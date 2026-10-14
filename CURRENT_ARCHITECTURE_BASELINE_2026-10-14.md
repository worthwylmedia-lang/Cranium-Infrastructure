# Convertible Cranium — Current Architecture Baseline

**Effective:** 2026-10-14
**Status:** Canonical documentation baseline for the acquisition binder
**Creator / intended personal IP owner:** William (Wyl) Mathes, subject to legal chain-of-title verification.

## 1. Canonical model

Convertible Cranium uses a **Dual-Substrate / Quad-Engine** governance architecture. The four engines are:

1. **Engine 1: Convertible Cranium Synapse** — proposal/context processing, evidence binding, assessment, and trace commitment.
2. **Engine 2A: Constitutional Authority substrate** — independent constitutional admissibility assessment, asking “May We?”
3. **Engine 2B: Evidence Grounding substrate** — independent evidence provenance, integrity, contradiction, relevance, and sufficiency assessment, asking “Is It So?”
4. **Engine 3: Convertible Cranium Kernel** — canonical convergence, authority transition, durable commit, receipt, proof, and lineage.

Cranium AI is a cognition/application surface, not an additional authority-path engine. Cranium Listener is untrusted ingress. Commander OS is the operational interface. Miracle Memory provides governed continuity. Circuit Breaker / COMA supplies cross-cutting containment and recovery.

## 2. Canonical authority invariant

**Cognition may come from anywhere. Authority comes only through Convertible Cranium.**

No model output, evidence bundle, memory record, UI state, runtime signal, receipt, attestation, or substrate finding can create or substitute for canonical Kernel authority.

Substrates A and B have distinct responsibilities and independently bound policies/formulas. Neither substrate grants authority. Convergence is not voting. The Kernel alone determines whether the required conditions support an authority transition; otherwise the request is denied, rejected, or quarantined according to the applicable contract.

## 3. Canonical path

```text
UNTRUSTED INGRESS
      |
   LISTENER
      |
ENGINE 1: SYNAPSE
proposal + context + evidence binding + trace
      |
      +---------------------------+
      |                           |
      v                           v
ENGINE 2A                    ENGINE 2B
SUBSTRATE A                  SUBSTRATE B
Constitutional Authority     Evidence Grounding
"May We?"                    "Is It So?"
      |                           |
      +-------------+-------------+
                    |
             ENGINE 3: KERNEL
        convergence + authority transition
                    |
            GOVERNED EXECUTION
                    |
          RECEIPT / PROOF / LINEAGE
```

## 4. Engine contracts

### Engine 1: Synapse
**Input:** untrusted request, context, and evidence.
**Output:** bounded proposal, context derivation, evidence references, assessment/attestation, and trace.
**Authority:** none.
**Failure posture:** reject, quarantine, or return insufficient evidence under the applicable contract.

### Engine 2A: Constitutional Authority
**Input:** normalized proposal and independently bound context.
**Output:** constitutional finding from the A1/A2 evaluation path.
**Question:** “May we?”
**Authority:** none. This is a governance input, not a canonical grant.

### Engine 2B: Evidence Grounding
**Input:** normalized proposal and evidence set.
**Output:** grounding finding from the B1/B2 evaluation path.
**Question:** “Is it so?”
**Authority:** none. This is an evidence-grounding input, not a canonical grant.

### Engine 3: Convertible Cranium Kernel
**Input:** proposal, Substrate A and B findings, authorization context, evidence lineage, and applicable version bindings.
**Output:** canonical transition or explicit rejection/denial/quarantine.
**Authority:** sole canonical authority source.
**Required controls:** identity/capability, proposal integrity, evidence and version binding, replay protection, current-state checks, convergence, transition construction, durable commit, and receipt/lineage.

## 5. Continuity and cross-cutting safety

- **Miracle Memory:** governed continuity, identity, contradiction handling, provenance, quarantine, snapshots, and recovery context.
- **Metabolic Memory v2:** resource governance over memory atoms; it does not grant authority. Locked/identity atoms are protected from flux eviction under the documented rules.
- **Circuit Breaker / COMA:** containment, freeze/quarantine, evidence preservation, recovery, and controlled resume; it is not a competing authority engine.
- **Receipts / attestation:** evidence and provenance for governed transitions, not authority issuers.

## 6. Historical terminology

The former Eight-Plane, Dual-Engine, and earlier juror-centered descriptions may be retained only as clearly labeled historical framing. They are not the current canonical architecture.

## 7. Documentation and evidence rule

Every material architectural claim should resolve to a component contract, source location, executable test or explicitly labeled evidence gap, and exact revision where applicable. Architecture documentation does not substitute for executable verification, independent review, runtime validation, or legal diligence.

## 8. Current evidence boundary

The binder records a project-run Kernel verification checkpoint at `0d0ae41f78e3f23da073390285d401c4a215dc6a` dated 2026-09-30. That checkpoint is self-attested project evidence, not an independent audit and not a claim that every later revision has been independently verified.

The Chromium Edition remains staged integration work until native x86-64 image build, boot, runtime acceptance, and verified-boot/rootfs evidence are captured. No HSM/KMS-backed custody, invulnerability, independent security certification, market validation, legal novelty, or patentability is claimed.

## 9. Ownership posture

The project records William (Wyl) Mathes as the intended personal IP owner for the work covered by the acquisition materials, subject to counsel's verification of chain of title, assignments, contributors, licenses, and third-party obligations. Repository and commit history are technical provenance, not by themselves proof of legal title.
