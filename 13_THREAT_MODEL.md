# Convertible Cranium Threat Model
**Status:** Architecture and diligence record
**Date:** 2026-09-30

## 1. Scope
This threat model covers the governed-intelligence boundary: human intent, AI proposals, evidence assessment, authority decisions, execution, continuity, and recovery.

It does not claim to replace a formal product security assessment, penetration test, or deployment-specific threat model.

## 2. Primary assets
- Canonical authority state
- Constitution and Prime Directives
- Capability and scope decisions
- Cryptographic keys and trust material
- Receipts and evidence chains
- Miracle Memory continuity state
- Runtime checkpoints and recovery state
- Private Wyl voice material
- AI runtime credentials
- Chromium Edition release provenance

## 3. Principal adversaries
### Prompt or context attacker
Attempts to make cognition override authority through instructions, retrieved content, tool output, or context poisoning.

### Capability attacker
Attempts to invoke a tool or capability outside the authorized scope.

### Replay attacker
Attempts to reuse an old authorization, receipt, session, or state transition.

### Evidence attacker
Attempts to alter, forge, or substitute evidence used by Synapse or the Kernel.

### Delegation attacker
Attempts to make a lower-trust agent or remote peer appear to possess the authority of a trusted principal.

### Runtime attacker
Attempts to bypass the execution boundary, continue after containment, or operate after a circuit-breaker trip.

### Supply-chain attacker
Attempts to introduce malicious dependencies, build inputs, release artifacts, or signing material.

## 4. Core mitigations
The architecture uses separate cognition and authority boundaries, fail-closed execution, cryptographic identity and receipts, replay checks, bounded evidence assessment, quarantine paths, lifecycle controls, and circuit-breaker recovery.

The verified Kernel diligence run on 2026-09-30 passed the repository's denial-semantics suite and session circuit-breaker checks, including replay rejection, evidence tamper rejection, generation fencing, rollback, and half-open recovery.

## 5. External comparison
NVIDIA OpenShell currently documents kernel-level runtime enforcement, default-deny policy, credential brokering, and a fail-closed sandbox boundary. Microsoft Agent Governance Toolkit documents fail-closed enforcement, deterministic replay, append-only audit, Merkle audit chains, circuit breakers, and delegated trust controls. OpenAI documents tool guardrails and explicit human approval before side effects. AWS documents runtime IAM/resource policies and temporal authorization.

These are concrete security mechanisms in adjacent systems. They should be treated as evidence that the threat space is real, not as evidence that any one comparator reproduces Convertible Cranium.

## 6. Known research limitation
A public issue in Google ADK reports a potential A2A human-confirmation bypass in a particular configuration. The issue is an external report, not a finding about Google ADK as a whole, and it illustrates why approval identity must be bound to the actual authority boundary rather than inferred from message shape.

## 7. Diligence boundary
This document is an architectural threat model. It is not a claim of immunity, certification, or complete security coverage. Deployment-specific controls, hardware trust, secret management, network isolation, ChromiumOS verified boot, and production operations require their own evidence.


## 8. Expanded OS-grade threat taxonomy

The threat model is organized by the boundary an adversary attempts to cross. This prevents the security analysis from collapsing every failure into generic "AI safety."

### 8.1 Cognitive-layer threats

These target proposal generation rather than canonical authority:

- Prompt-conditioning attacks
- Context poisoning
- Semantic jailbreaks
- Tool-call hallucination
- Instruction-hierarchy manipulation
- Adversarial ambiguity designed to induce unsafe proposals

**Controls:** proposal/authority separation, bounded Synapse assessment, constitutional constraints, and fail-closed Kernel authorization.

A successful cognitive attack can produce a bad proposal. It must not thereby produce an authorized operation.

### 8.2 Authority-layer threats

These target the canonical authority boundary itself:

- Replay of previously authorized operations
- Receipt-chain tampering
- Delegation spoofing
- Authority-surface impersonation
- Key or issuer substitution
- Capability or scope escalation
- Lifecycle-state bypass

**Controls:** canonical issuer validation, Ed25519 verification, receipt integrity, replay denial, capability/scope checks, lifecycle controls, and fail-closed execution.

The authority layer is the highest-consequence boundary because compromise here can convert otherwise contained cognition into real authority.

### 8.3 Evidence-layer threats

These target the assessment plane:

- Fabricated evidence injection
- Misleading evidence selection
- Assessment-bias manipulation
- Stale evidence presented as current
- Cross-session contamination
- Evidence provenance substitution

**Controls:** bounded evidence evaluation, attestation separation, provenance, cryptographic integrity, contradiction handling, and constitutional invariants.

Evidence can inform an authority decision without becoming the authority source itself.

### 8.4 Continuity-layer threats

These exploit memory and historical state:

- Historical-authority inference
- Journal/state mutation
- Identity drift across sessions
- Canon/provisional-state confusion
- Memory poisoning
- Recovery-state manipulation

**Controls:** governed continuity, contradiction detection, quarantine, journal integrity, explicit memory classes, identity binding, and controlled recovery.

A remembered fact is not automatically a permission. A prior authorization is not automatically a current authorization.

### 8.5 Execution-layer threats

These target Commander and the boundary between authorization and side effect:

- UI-authority confusion
- Local evaluator injection
- Execution-path subversion
- Client-side grant logic
- Unauthorized tool substitution
- False completion reporting

**Controls:** Commander package boundary, AuthorityBridge separation, governed execution paths, explicit result states, and prohibition on browser/UI-local authority.

### 8.6 Runtime-layer threats

These target continued operation and recovery:

- Resource exhaustion

## 8.1 Cryptographic custody limitation

The current Wave V hardening adds an in-process HMAC custody proof to the tested canonical CORE signing path. This raises the bar above possession of a trusted Ed25519 private key alone, but it is **not an HSM, hardware-backed key boundary, secure enclave, TPM-backed signer, or remote process attestation system**.

The custody key is generated and held in application process memory. A process compromise that can control the canonical signing process may therefore be able to operate within the same trust boundary. Restart continuity for this custody secret is a separate design concern and must not be represented as durable external custody.

Production-grade deployment should place high-value signing and custody material behind an external HSM/KMS, hardware-backed signer, or appropriately attested custody service, with explicit lifecycle, rotation, revocation, and recovery evidence.

The current evidence therefore supports the narrower statement: **the tested canonical custody path rejects a valid CORE signature that lacks the required process-local custody proof.** It does not support a claim that stolen key material is useless under all deployment conditions.

## 12. Multi-vector attack and cross-layer escalation

A governed-intelligence threat model cannot assume that an adversary attacks one component at a time. The higher-consequence failure mode is often a **multi-vector attack** in which several individually bounded signals are chained across architectural boundaries.

The security objective is therefore not merely to stop each vector independently. It is to prevent composition of non-authoritative signals from synthesizing authority.

### 12.1 The authority-synthesis problem

Consider an adversarial sequence:

```text
Prompt manipulation
      |
      v
Context poisoning
      |
      v
Persuasive AI proposal
      |
      v
Manipulated / selective evidence
      |
      v
Memory supplies historical precedent
      |
      v
Commander presents familiar workflow
      |
      v
Downstream component infers permission
      |
      X
      |
  KERNEL BOUNDARY
      |
   DENIED / GOVERNED
```

Each preceding signal may appear plausible in isolation. The architectural requirement is that their combination must not create an authority that none of them possesses individually.

### 12.2 Multi-vector principle

**No combination of non-authoritative signals may synthesize canonical authority.**

This includes combinations of:

- model confidence
- retrieved context
- historical memory
- evidence assessments
- previous successful operations
- user-interface state
- delegated-agent assertions
- tool responses
- stale receipts
- external messages
- local application state

A system that treats accumulated persuasion as permission has allowed authority to emerge implicitly.

Convertible Cranium requires authority to remain an explicit governed transition.

### 12.3 Representative attack chains

#### Chain A: Cognitive-to-authority escalation

`prompt attack -> unsafe proposal -> scope manipulation -> attempted execution`

**Containment boundary:** Synapse assessment and Kernel capability/scope enforcement.

The cognitive attack may succeed at influencing the proposal. It must not succeed at changing canonical authority.

#### Chain B: Continuity-to-authority escalation

`memory poisoning -> historical precedent -> identity drift -> inferred permission -> execution attempt`

**Containment boundary:** governed Miracle Memory plus identity, lifecycle, and Kernel authorization controls.

Prior success is evidence about history. It is not a current authorization.

#### Chain C: Evidence-to-authority escalation

`fabricated evidence -> assessment manipulation -> favorable assessment -> authority request`

**Containment boundary:** Synapse evidence integrity plus independent Kernel decision.

A favorable assessment remains an assessment. It does not become a grant merely because the assessment is persuasive.

#### Chain D: UI-to-execution escalation

`UI compromise -> false authorization display -> operator trust -> uncontrolled execution path`

**Containment boundary:** Commander package boundary and prohibition on UI-local authority.

The visual presentation of an authorization state must not itself create that state.

#### Chain E: Agent-to-agent authority laundering

`agent A proposes -> agent B "approves" -> agent C executes`

**Containment boundary:** canonical issuer and Kernel authority boundary.

Delegation cannot manufacture authority by multiplying the number of agents that agree.

#### Chain F: Supply-chain-to-authority escalation

`dependency compromise -> altered runtime -> authority-surface substitution -> malicious execution`

**Containment boundary:** build/release provenance, artifact integrity, protected release paths, and independent canonical authority validation.

This chain demonstrates an important limitation: authority architecture does not eliminate the need for trustworthy build and deployment infrastructure.

#### Chain G: Replay-to-continuity escalation

`old authorization -> replay -> restored context -> memory persistence -> new execution attempt`

**Containment boundary:** replay denial, generation fencing, lifecycle controls, receipt integrity, and governed continuity.

Historical authority must remain historical unless a new governed transition establishes current authority.

### 12.4 Cross-layer escalation graph

The following abstraction identifies the major surfaces an attacker may attempt to chain:

```text
          COGNITION
              |
       +------+------+
       |             |
       v             v
    CONTEXT        TOOLS
       |             |
       +------+------+
              |
              v
           SYNAPSE
       evidence / trust
              |
       +------+------+
       |             |
       v             v
    MEMORY        IDENTITY
       |             |
       +------+------+
              |
              v
           KERNEL
      canonical authority
              |
       +------+------+
       |             |
       v             v
    COMMANDER     RUNTIME
       |             |
       +------+------+
              |
              v
        SIDE EFFECT
              |
              v
       RECEIPT / MEMORY
              |
              v
      CIRCUIT BREAKER
        / COMA
```

The graph is intentionally not a claim that every deployment has every surface connected identically. It is a threat-analysis model for identifying where trust or authority could be accidentally transferred between layers.

### 12.5 Composition-resistance invariant

A multi-vector attack is successful if individually non-authoritative conditions compose into an unauthorized side effect.

The required invariant is therefore:

**If no canonical authority transition has granted the operation, cross-layer accumulation of confidence, context, evidence, identity, precedent, or UI state cannot make the operation authorized.**

This gives the architecture a concrete security property to test.

It is not enough to test:

- "Does the prompt attack fail?"
- "Does replay fail?"
- "Does evidence tampering fail?"

The stronger questions are:

- Does prompt manipulation followed by evidence manipulation still fail?
- Does memory poisoning followed by identity drift still fail?
- Does a stale receipt combined with a fresh-looking session still fail?
- Does a compromised UI combined with a valid historical authorization still fail?
- Does agent A's proposal combined with agent B's assertion create authority?
- Does a runtime recovery path accidentally restore authority that the new generation does not possess?

These are **multi-vector conformance questions**.

### 12.6 Security significance

The purpose of this model is not to claim that multi-vector attacks are impossible. No serious security architecture can promise that.

The purpose is to ensure that the architecture has a place where attack composition stops.

That place is the canonical authority boundary.

Cognition can be compromised.

Evidence can be misleading.

Memory can be poisoned.

A UI can be deceptive.

A session can become stale.

A dependency can be compromised.

Multiple such conditions can occur together.

The architectural requirement remains unchanged:

**None of them, individually or in combination, becomes canonical authority merely by accumulating persuasive signals.**

### 12.7 Test-design implication

The next generation of Cranium security testing should include chained attack scenarios in addition to isolated denial tests.

A multi-vector test should identify:

1. Initial attack vector.
2. Secondary vector.
3. Cross-layer boundary being targeted.
4. Expected containment point.
5. Canonical authority state before the attempted escalation.
6. Whether any unauthorized state transition occurred.
7. Receipt/evidence produced by the denial or containment.
8. Recovery behavior, if applicable.
9. Final authority state.

This creates a bridge between the architectural threat model and executable acquisition/security diligence.
