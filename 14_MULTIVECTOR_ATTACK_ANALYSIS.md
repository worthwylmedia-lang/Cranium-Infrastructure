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
