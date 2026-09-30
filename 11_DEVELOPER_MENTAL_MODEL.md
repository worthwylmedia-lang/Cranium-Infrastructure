# Convertible Cranium Developer Mental Model
**Status:** Engineering guide
**Date:** 2026-09-30

## The one sentence
Build intelligence as if it is powerful but untrusted, and build authority as if it is scarce, explicit, inspectable, and independently enforceable.

## The layers
**Commander** is the operator surface. It presents state, intent, evidence, and outcomes.

**Cranium AI** is the cognition/orchestration layer. It can reason, plan, summarize, retrieve, and propose. It cannot independently confer authority.

**Synapse** is the evidence and assessment boundary. It determines whether the proposal has sufficient bounded evidence and trust context for the next authority decision.

**Kernel** is the canonical authority source. It enforces the constitutional and capability boundary.

**Miracle Memory** is governed continuity. Memory is state with provenance and lifecycle, not a magical bucket of facts.

**Circuit Breaker / COMA** is containment and recovery. A critical state can stop progression, roll back to a known checkpoint, and require controlled recovery.

## Developer rule zero
Never implement a side effect by asking the model whether it is allowed.

The model can request an action. The authority layer decides whether that action may occur.

## State discipline
Do not collapse proposal into authorization.
Do not collapse authorization into execution.
Do not collapse execution into completion.
Do not treat an error message as a denial receipt unless the authority layer actually produced the denial.
Do not let UI state become the source of truth for governance state.

## Integration pattern
'Intent -> AI proposal -> Synapse assessment -> Kernel decision -> governed execution -> receipt -> continuity'

Failure paths must be explicit:
'uncertain -> assess'
'denied -> stop'
'tampered -> reject/quarantine'
'replayed -> reject'
'critical -> circuit breaker'
'recoverable -> checkpoint/rollback -> controlled recovery'

## What developers should never assume
A model's confidence is not authority.
A user's request is not automatically sufficient authorization for every downstream action.
A trusted UI is not proof of a trusted state transition.
A successful tool invocation is not proof that the action was authorized.
A stored memory is not automatically canonical truth.

## Why this matters for Chromium Edition
ChromiumOS supplies the operating environment. Convertible Cranium supplies the governed-intelligence architecture layered into that environment. The browser, shell, applications, and host experience remain distinct from the authority substrate.

The product can therefore feel familiar at the OS level while maintaining a different rule for consequential intelligence: the model proposes, the substrate decides.
