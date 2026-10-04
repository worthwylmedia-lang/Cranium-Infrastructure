# Convertible Cranium Authority Flow
**Status:** Technical architecture record
**Date:** 2026-09-30

## Purpose
This document defines the governed transition from an AI-generated proposal to an executable system action.

The central rule is simple: cognition may propose; authority must be separately established.

## Canonical flow
1. **Listener** receives intent as untrusted ingress and cannot authorize.
2. **Commander OS** establishes the operational context for the requested action.
3. **Cranium AI** interprets intent and proposes a candidate action or plan.
4. **Synapse** evaluates evidence, scope, risk, provenance, and trust conditions.
5. **Governance Review Juror One** performs constructive coherence and evidence-sufficiency review.
6. **Governance Review Juror Two** performs independent adversarial contradiction, boundary, and rejection-condition review.
7. **Kernel** evaluates the governed request against constitutional authority, capabilities, receipts, replay state, lifecycle state, applicable constraints, and the review results. The Kernel alone issues canonical authority.
8. **Commander OS / governed runtime** executes only an authorized transition. It does not grant authority.
9. **Miracle Memory** records authorized continuity, contradiction, journal state, identity, and recovery-relevant evidence.
10. **Circuit Breaker / COMA** can interrupt, quarantine, roll back, or prevent continuation when critical conditions are detected.

## Authority boundary
The model is not the authority source.
The UI is not the authority source.
The operator guide is not the authority source.
A tool is not the authority source.
The Kernel is the canonical authority boundary.

## Consequential action invariant
A proposal, preview, explanation, or simulation must never be represented as a completed action merely because an AI produced it.

The system must distinguish at minimum:
- proposed
- assessed
- authorized
- denied
- quarantined
- executing
- completed
- recovered

These states are evidence-bearing system states, not presentation labels.

## Why this architecture exists
Conventional agent loops often place reasoning, tool selection, and execution in one application flow. Convertible Cranium separates those concerns so that a capable model can remain useful without becoming the issuer of authority.

## Comparator context
NVIDIA OpenShell demonstrates a related external enforcement pattern: agents operate inside sandboxes while a trusted supervisor mediates policy, credentials, and network access. OpenAI documents tool guardrails and human approval as controls around side effects. AWS AgentCore provides runtime authorization and resource/IAM policy controls. Microsoft Agent Governance Toolkit documents policy enforcement, fail-closed behavior, audit chains, replay, and circuit breakers.

Those are important adjacent implementations. They establish that pieces of the problem are independently recognized and actively engineered. They do not establish that those systems are the Convertible Cranium architecture.

## Evidence rule
Any claim about implementation must be tied to repository evidence, executable verification, or a clearly identified external source. Architectural language must not be inflated into a claim of certification, patentability, or universal novelty.

## Current architecture baseline

This document is part of the current Convertible Cranium documentation set. The canonical architecture is Dual-Substrate / Quad-Engine: Cranium AI, Synapse, Governance Review Juror One, and Governance Review Juror Two. The jurors have deliberately different review mandates and processes and neither issues authority.

Commander OS is the operational control surface. Cranium Listener is untrusted ingress. Miracle Memory provides governed continuity. Circuit Breaker / COMA provides cross-cutting runtime containment and recovery. The Convertible Cranium Kernel remains the sole canonical authority source.

The former Eight-Plane and Dual-Engine descriptions are historical framing only and must not be read as the current governance model.
