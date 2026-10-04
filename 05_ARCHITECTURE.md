# Convertible Cranium Architecture

## Dual-Substrate / Quad-Engine Architecture

Convertible Cranium is a governed-intelligence infrastructure architecture designed to separate cognition, assessment, independent governance review, and canonical authority while binding continuity, execution, recovery, and evidence to explicit governance boundaries.

### Current architecture baseline

The current canonical architecture is Dual-Substrate / Quad-Engine. The earlier Dual-Engine and Eight-Plane descriptions are historical framing and must not be used as the current governance model.

#### Four engines across two governance substrates

1. Cranium AI: intelligence and orchestration. It interprets intent, generates proposals, coordinates bounded work, and remains non-authoritative.
2. Synapse: evidence and assessment. It evaluates evidence, trust conditions, and risk-relevant signals within explicit contracts and remains non-authoritative.
3. Governance Review Juror One: independent constructive review focused on coherence, justification, evidence sufficiency, and whether a proposed transition is supportable.
4. Governance Review Juror Two: independent adversarial review focused on contradiction, failure modes, boundary violations, unacceptable conditions, and whether a proposed transition must be rejected.

The two jurors are intentionally constituted with different review mandates and processes. They are reviewers, not authority issuers.

#### Authority boundary

The Convertible Cranium Kernel is the sole canonical authority source. No engine, juror, UI, memory record, runtime state, receipt, external attestation, or consensus can create or substitute for Kernel authority.

#### Operational and safety surfaces

- Commander OS is the operational control surface.
- Cranium Listener is untrusted ingress and must not be treated as an authority source.
- Miracle Memory provides governed continuity, contradiction handling, quarantine, identity, journal, and recovery context.
- Circuit Breaker / COMA provides cross-cutting runtime containment, checkpoint rollback, fencing, and bounded recovery.
- Receipts / attestation provide evidence of governed transitions and provenance; they do not issue authority.

#### Governed path

Listener → AI proposal → Synapse assessment → independent Juror One / Juror Two review → governed request → Kernel decision → execution → receipt → Miracle Memory

Circuit Breaker / COMA may interrupt or roll back the runtime path according to its explicit safety contract. It does not become a second authority source.

#### Historical terminology

The former Eight-Plane model remains useful as a historical subsystem taxonomy. The former Dual-Engine model remains useful as an earlier conceptual distinction between cognition and authority. Neither is the current canonical architecture.

## Architecture thesis

Cognition may propose. Evidence may inform. Independent review may challenge or support a proposed transition. Only the Kernel can issue canonical authority.

The architecture is deliberately resistant to authority emergence through composition. A persuasive model output, favorable evidence, two agreeing jurors, a UI state, a memory record, an external attestation, or a runtime signal cannot become authority merely by being combined.

## Acquisition boundary

The canonical Kernel implementation remains separately maintained. The acquisition-facing repository documents the architecture and evidence boundary without implying transfer of all underlying platform IP, future improvements, private assets, or third-party rights.

See the authority flow, threat model, verification record, and IP/product boundary for detailed evidence and limitations.
