# Convertible Cranium — Current Architecture Baseline

**Effective:** 2026-10-02
**Status:** Canonical documentation baseline

## Current model

Convertible Cranium is a **Dual-Substrate / Quad-Engine** governance architecture.

The four engines are:

1. Cranium AI: intelligence and orchestration.
2. Synapse: evidence and assessment.
3. Governance Review Juror One: constructive coherence, justification, and evidence-sufficiency review.
4. Governance Review Juror Two: adversarial contradiction, failure-mode, boundary, and rejection-condition review.

The two jurors deliberately use different mandates and processes. Neither juror issues canonical authority.

## Canonical authority

The **Convertible Cranium Kernel is the sole canonical authority source**.

No model output, evidence bundle, memory record, UI state, runtime state, receipt, attestation, consensus, or juror decision can create or substitute for Kernel authority.
## Runtime surfaces

- Commander OS: operational control surface.
- Cranium Listener: untrusted ingress.
- Miracle Memory: governed continuity, identity, contradiction, quarantine, journal, and recovery context.
- Circuit Breaker / COMA: cross-cutting runtime containment and recovery.
- Receipts / Attestation: evidence and provenance of governed transitions.

## Governed path

Listener → AI proposal → Synapse assessment → Juror One / Juror Two review → governed request → Kernel decision → execution → receipt → Miracle Memory

Circuit Breaker / COMA may interrupt or roll back the runtime path under its safety contract without becoming an authority source.

## Retired terminology

The **Eight-Plane Architecture** and **Dual-Engine** descriptions are historical framing. They may be retained when documenting architectural history, but they must not be presented as the current governance architecture.

## Documentation rule

Any document describing the current architecture must agree with this baseline. Historical documents may preserve prior terminology only when the historical status is explicit.

## Evidence rule

Architecture documentation describes boundaries. It does not substitute for executable evidence, independent review, runtime validation, or legal diligence.

## Implementation status boundary

This file defines the canonical documentation architecture. It does not assert that every named component is implemented in the production codebase. See `40_IMPLEMENTATION_STATUS_AND_GAP_REGISTER.md` for the component-by-component evidence status and remediation gates.
