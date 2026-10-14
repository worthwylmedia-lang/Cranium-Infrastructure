# Convertible Cranium Architecture

## Dual-Substrate / Quad-Engine Governance Architecture

Convertible Cranium is an authority-bound governance architecture designed to separate cognition, evidence, constitutional admissibility, and canonical authority. Its operating principle is:

> **Cognition may come from anywhere. Authority comes only through Convertible Cranium.**

The canonical architecture has four engines. The two middle engines are independent governance substrates with different constitutions, responsibilities, and evaluation paths.

## Canonical path

```text
UNTRUSTED INGRESS
        |
     LISTENER
        |
 ENGINE 1 · SYNAPSE
 proposal / context / evidence binding / trace
        |
        +--------------------------------+
        |                                |
 ENGINE 2A · SUBSTRATE A          ENGINE 2B · SUBSTRATE B
 Constitutional Authority        Evidence Grounding
 "MAY WE?"                       "IS IT SO?"
        |                                |
        +----------------+---------------+
                         |
              ENGINE 3 · CRANIUM KERNEL
          canonical convergence and authority
                         |
                GOVERNED EXECUTION
                         |
              RECEIPT / PROOF / LINEAGE
```

## Engine responsibilities

### Engine 1: Convertible Cranium Synapse

Synapse handles bounded proposal/context processing, evidence binding, assessment, attestation, and trace commitment. It prepares information for governance review but cannot grant canonical authority.

### Engine 2A: Constitutional Authority

Substrate A evaluates constitutional admissibility, policy constraints, scope, prohibited actions, approval requirements, and applicable version bindings. Its governing question is **“May we?”** The A1/A2 path supplies an independently constituted finding. That finding is an input to the Kernel, not an authority grant.

### Engine 2B: Evidence Grounding

Substrate B evaluates evidence provenance, integrity, contradiction, freshness/relevance, and sufficiency. Its governing question is **“Is it so?”** The B1/B2 path supplies an independently constituted finding. That finding is an input to the Kernel, not an authority grant.

Substrates A and B must not be collapsed into duplicate evaluators that deterministically reproduce the same judgment. They have distinct policies, formulas, and responsibilities while sharing the principle **Truth above all**.

### Engine 3: Convertible Cranium Kernel

The Kernel is the sole canonical authority source. It validates the required proposal, authorization context, A/B findings, evidence and version bindings, replay/idempotency boundary, current state, and convergence conditions. It then either performs the governed authority transition with durable commit and receipt/lineage or fails closed according to the applicable contract.

**Convergence is not voting.** Neither substrate is authoritative, and no model output, UI state, memory record, external attestation, receipt, or runtime signal can substitute for the Kernel.

## Other system surfaces

- **Cranium AI:** cognition/application surface for intelligence and orchestration; not an additional authority-path engine.
- **Cranium Listener:** untrusted ingress.
- **Convertible Cranium Commander OS:** operational control surface and human-facing workspace; it does not grant authority.
- **Miracle Memory:** governed continuity, identity, provenance, contradiction handling, quarantine, snapshots, and recovery context.
- **Metabolic Memory v2:** resource governance over memory atoms; it does not grant authority and protects locked/identity atoms from flux eviction under its documented rules.
- **Circuit Breaker / COMA:** cross-cutting containment, freeze/quarantine, evidence preservation, recovery, and controlled resume.
- **Receipts / attestation:** evidence and provenance of governed transitions; they do not issue authority.

## Historical terminology

The former Eight-Plane, Dual-Engine, and earlier juror-centered descriptions may be retained only as clearly labeled historical framing. They must not be presented as the current canonical governance path.

## Acquisition and evidence boundary

This binder is an architecture and evidence index, not a second implementation of the Kernel. Every material claim should trace to the exact repository/revision, component contract, test or artifact, and evidence status.

A documented architecture is not itself proof of implementation. Project-run verification is not independent third-party audit. Staged Chromium Edition integration is not a completed production ChromiumOS release. Chain of title, patentability, legal novelty, market demand, and third-party rights require separate diligence.
