# Convertible Cranium Authority Flow

**Status:** Canonical architecture explanation; implementation evidence is tracked separately.

## Purpose

Describe the governed transition from untrusted input to a consequential action while keeping cognition, review, and canonical authority separate.

## Canonical path

1. **Listener** receives intent as untrusted ingress.
2. **Engine 1, Synapse** creates a bounded proposal, binds context and evidence, performs assessment, and commits the relevant trace. Synapse cannot authorize.
3. **Engine 2A, Substrate A: Constitutional Authority** evaluates constitutional admissibility, scope, prohibited actions, and approval requirements. It asks **“May we?”**
4. **Engine 2B, Substrate B: Evidence Grounding** evaluates evidence provenance, integrity, contradiction, relevance/freshness, and sufficiency. It asks **“Is it so?”**
5. **Engine 3, Convertible Cranium Kernel** checks the proposal, A/B findings, authorization context, evidence/version bindings, replay state, current state, and convergence conditions. The Kernel alone grants or denies canonical authority.
6. **Governed execution** follows only a valid Kernel authority transition.
7. **Receipt, proof, and lineage** record the governed outcome. They provide evidence, not authority.

**Cranium AI** is a cognition/application surface, not an additional authority-path engine. **Commander OS** is the operational control surface and cannot grant authority. **Miracle Memory** supports governed continuity. **Circuit Breaker / COMA** may interrupt, quarantine, or support controlled recovery under its safety contract.

## Authority boundary

- A model is not the authority source.
- A UI or operator guide is not the authority source.
- A substrate finding is not the authority source.
- A receipt, attestation, memory record, or runtime signal is not the authority source.
- The Convertible Cranium Kernel is the sole canonical authority boundary.

**Convergence is not voting.** Required conditions must be satisfied under the applicable Kernel contract; otherwise the request fails closed or is rejected/quarantined as defined by that contract.

## Consequential-action invariant

A proposal, preview, explanation, simulation, or tool plan must not be represented as a completed action merely because an AI produced it. System state should distinguish proposed, assessed, authorized, denied, quarantined, executing, completed, and recovered outcomes.

## Evidence rule

Any claim about implementation must be tied to an exact repository/revision, executable verification or artifact, environment, and evidence status. Architecture documentation is not certification, patentability evidence, or proof of universal novelty. Chromium Edition build, boot, runtime, and verified-boot claims remain pending until supported evidence is captured.
