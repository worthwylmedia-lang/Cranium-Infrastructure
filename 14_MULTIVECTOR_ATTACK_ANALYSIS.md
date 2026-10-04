# Multi-Vector Attack Analysis

Cross-plane attacks attempt to turn individually valid signals into unauthorized authority.

## Core Invariant

> No combination of non-authoritative signals may synthesize canonical authority.

### Attack Classes

- Cognition → authority: model output attempts to self-approve.
- Continuity → authority: memory state is treated as permission.
- Evidence → authority: valid-looking evidence is treated as authorization.
- UI → execution: interface state is mistaken for a governed transition.
- Agent-to-agent laundering: one agent treats another agent's proposal as authority.
- Supply chain → authority: compromised dependencies attempt to alter the authority boundary.
- Replay → continuity: stale receipts or sessions attempt to regain authority.

## Control Principle

Every consequential transition must cross the canonical Kernel boundary. Non-authoritative signals may inform assessment but cannot collectively substitute for Kernel issuance.

The analysis is non-exhaustive. Each attack class requires executable validation in the implementation exposing the relevant path.

### Evidence-count rule

Large attack totals are not evidence by themselves. Aggregate counts may only be reported as executed results when each underlying case is bound to a real executable path and captured output. A manifest, generator, or planned workload is a test plan, not a completed attack result.

The implementation-status register records this distinction explicitly.

## Current architecture baseline

This document is part of the current Convertible Cranium documentation set. The canonical architecture is Dual-Substrate / Quad-Engine: Cranium AI, Synapse, Governance Review Juror One, and Governance Review Juror Two. The jurors have deliberately different review mandates and processes and neither issues authority.

Commander OS is the operational control surface. Cranium Listener is untrusted ingress. Miracle Memory provides governed continuity. Circuit Breaker / COMA provides cross-cutting runtime containment and recovery. The Convertible Cranium Kernel remains the sole canonical authority source.

The former Eight-Plane and Dual-Engine descriptions are historical framing only and must not be read as the current governance model.
