# Convertible Cranium — Implementation Status and Gap Register

**Effective:** 2026-10-03
**Purpose:** Keep the acquisition-facing architecture synchronized with executable implementation evidence.

## Rule

The architecture baseline is canonical documentation. It is not, by itself, proof that every named component has been implemented in the production repositories.

Every component in the current model therefore carries an implementation status. A status may only move to **Implemented and Verified** when a concrete repository artifact, executable test, or independently reproducible result supports that claim.

This register is intentionally conservative. It reflects the 2026-10-03 private-repository audit available to the project plus the public acquisition binder. It does not manufacture evidence for inaccessible or unimplemented components.

## Evidence labels

| Label | Meaning |
|---|---|
| **Implemented and verified** | Concrete implementation and executable/reproducible evidence are present within the stated scope. |
| **Implemented, not yet verified** | Implementation exists, but the required executable or reproducible verification has not been established here. |
| **Designed, not implemented** | The architecture is documented as current, but the audited implementation did not contain the named component or stage. |
| **Partially implemented** | Some supporting mechanisms exist, but the complete architectural contract is not yet implemented end to end. |
| **Blocked** | The work cannot be represented as complete because an identified environment, integration, or custody dependency remains. |
| **Not claimed** | The project deliberately makes no stronger assertion. |

## Current architecture register

| Component / boundary | Status | Evidence / limitation | Next gate |
|---|---|---|---|
| Cranium AI proposal/orchestration | **Not independently assessed here** | The private audit scope did not re-audit `cranium-ai`; no public binder text is treated as implementation proof. | Audit the implementation and bind it to the current contract. |
| Synapse evidence / attestation | **Implemented and verified within stated scope** | Private audit found the attestation contract and Kernel reference implementation aligned; standalone extraction is explicitly not claimed. | Preserve the non-authority boundary and add independent integration evidence when extracted. |
| Governance Review Juror One | **Designed, not implemented** | The 2026-10-03 private audit found zero private-code hits for the current juror terminology. | Implement as an independent review stage with a distinct mandate and evidence contract. |
| Governance Review Juror Two | **Designed, not implemented** | Same audit result; no private implementation artifact was found for the named juror. | Implement an adversarial review stage with distinct inputs, rules, and evidence. |
| Cranium Listener | **Designed, not implemented** | The audit found no private implementation identified as the current Listener component. | Implement and test untrusted-ingress boundaries before proposal admission. |
| Convertible Cranium Kernel | **Implemented and verified within stated scope** | SHA-256 hashing, replay handling, boundary validation, immutable reduction, denial semantics, Constitution checks, signing lifecycle, Synapse integration, and HTTP gateway plumbing were verified in the audited checkout. | Extend evidence as the architecture evolves; maintain Kernel-only authority. |
| Kernel canonical authority boundary | **Implemented and verified within stated scope** | The audited Kernel remains the sole canonical authority source within the repository architecture. | Independent review of the eight boundary rules and deployment-specific controls. |
| Commander OS | **Partially implemented** | The audited Commander surface contains no authority evaluator/reducer/receipt implementation, but `AuthorityBridge` is currently a fail-closed stub with no transport client. | Wire Commander to an authenticated local/remote Kernel adapter and verify the round trip. |
| HTTP substrate gateway | **Partially implemented** | Real HTTP servers exist, including `/v1/substrate/respond`; the audit found zero clients consuming the gateway. | Implement and verify the first real client path. |
| `/v1/authority/execute` | **Blocked** | The audited handler checks `evaluation.allowed`, but `evaluate()` returns `{ transition, replayStatus }`; the route therefore always fails closed. | Check the actual decision field and add a regression test. |
| `scripts/` type safety | **Partially implemented** | `tsconfig.json` excludes `scripts/`, allowing the gateway bug to escape normal lint/typecheck coverage. | Include executable scripts in typecheck or give them an equivalent compile-time validation gate. |
| Miracle Memory tiers | **Implemented within stated scope** | The audited Kernel implements `CONSTITUTIONAL`, `CANON`, `PROVISIONAL`, and `QUARANTINED` tiers with receipt-bound promotion. | Preserve tier evidence while reconciling the current domain model. |
| Miracle Memory three-domain model | **Designed, not implemented** | The current architecture names Cognitive/Governance/Quarantine domains and a provenance envelope, but the audited code exposes tiers rather than those domain fields. | Record an ADR defining how tiers map within domains, then implement the contract. |
| Session Circuit Breaker / COMA | **Implemented within stated scope** | The private audit found runtime circuit-breaker behavior and recovery checks, but deployment-specific enforcement remains separate evidence. | Maintain independent runtime and deployment validation. |
| Contradiction detection | **Partially implemented** | `CanonLane` uses keyword substring heuristics with hardcoded confidence values; this is a tripwire, not general semantic contradiction understanding. | Rename/label the mechanism honestly and test false-positive/false-negative behavior. |
| Requester authorization rule | **Partially implemented** | `RULE_04` uses string-prefix blocking for a small demo set; this must not be represented as production authentication or authorization. | Replace or supplement with real authenticated identity and policy enforcement. |
| Cryptographic custody | **Partially implemented** | The audited custody path adds process-local proof but explicitly is not HSM/KMS, hardware-backed custody, or remote attestation. | Define and validate a production custody architecture. |
| Acquisition stress suite | **Not claimed as executed** | The audit found a manifest/planning surface, not captured evidence for every stress case. | Execute each bound case and retain reproducible artifacts before publishing aggregate pass counts. |
| Vendor snapshot freshness | **Implemented, policy gap** | Spot checks found byte-consistent pinned snapshots, but a written staleness policy is still needed. | Define release-based re-vendoring and verification rules. |
| Kernel version references | **Open reconciliation** | The public binder references `0d0ae41`, while other live references resolve to `e36bdba`; the prior audit could not verify the newer hash through its toolset. | Reconcile the authoritative revision and publish one unambiguous pin. |

## Required order of remediation

### P0 — unblock truthful execution

1. Fix `/v1/authority/execute` against the actual `evaluate()` return contract.
2. Add the gateway regression test.
3. Put `scripts/` under compile-time validation.

### P1 — make the architecture executable

1. Implement the Commander `AuthorityBridge` transport against the authenticated gateway.
2. Implement the Listener boundary as untrusted ingress.
3. Implement Juror One and Juror Two as independent review stages with distinct mandates and contracts.
4. Demonstrate the complete path with a real receipt: Listener → proposal → assessment → reviews → Kernel decision → execution → receipt.

### P1 — reconcile continuity semantics

Document the relationship between Miracle Memory domains and implementation tiers before adding new persistence or migration behavior.

### P2 — strengthen the actual security gate

Review the eight boundary rules as the primary threat surface, replace demo authorization with real identity/policy enforcement, and test multi-vector composition without treating aggregate attack counts as evidence until the individual bindings execute.

### P2 — release hygiene

Reconcile the Kernel pin, formalize vendored-snapshot freshness, and keep the public binder synchronized with the release revision actually used for verification.

### P3 — high-value custody hardening

Move production signing/custody material behind an external HSM, KMS, hardware-backed signer, or appropriately attested custody service when the deployment boundary requires it.

## Acquisition interpretation

The current architecture is a **canonical design baseline with a mixed implementation state**. That is not a defect in itself. The defect would be presenting designed components as shipped, or treating documentation as execution evidence.

The acquisition binder therefore uses the following rule:

> **Architecture defines the intended boundary. Executable evidence determines implementation status. Kernel evidence determines canonical authority.**

## Related evidence

- `CURRENT_ARCHITECTURE_BASELINE_2026-10-02.md`
- `05_ARCHITECTURE.md`
- `13_THREAT_MODEL.md`
- `14_MULTIVECTOR_ATTACK_ANALYSIS.md`
- `17_VERIFICATION.md`
- `18_DILIGENCE.md`
- `35_BINDER_FINALIZATION_CHECKLIST.md`
- `39_WORTHWYL_STUDIO_HYBRID.md`
