# Governance Substrate Whitepaper

Convertible Cranium — A Canonical Authority-Bound Dual-Substrate / Quad-Engine Governance Substrate

This whitepaper presents Cranium as a proposed infrastructure category, describing its architectural thesis, authority invariant, dual-substrate / quad-engine model, threat landscape, verification evidence, and governance implications.

## Abstract

Convertible Cranium defines a proposed infrastructure category: the Infrastructure Ecosystem Authority-Bound Dual-Substrate / Quad-Engine Governance Substrate. It establishes a canonical authority boundary, separates cognition from permission, binds continuity to governance, defines deterministic execution and recovery boundaries, and provides verifiable receipts for consequential governed operations.

The Canonical Authority Invariant is the substrate's defining architectural property:

> No combination of non-authoritative signals may synthesize canonical authority.
> Authority exists only when the Kernel issues a governed transition.

## 1. Category Thesis

Governed intelligence requires more than safety heuristics or runtime policy enforcement. Cranium's architecture is designed to provide a canonical authority substrate.

Expand via 02_CATEGORY_DEFINITION.md.

## 2. Dual-Substrate / Quad-Engine Architecture

Cranium separates:

- Engine A — Cognition: Cranium AI, Synapse, Commander OS
- Engine B — Authority: Kernel, Constitution, Miracle Memory, COMA, Receipts

This separation is the defining architectural boundary.

Expand via 05_ARCHITECTURE.md.

## 3. Authority Invariant

The invariant prohibits non-authoritative components from becoming canonical authority, including:

- cognition
- evidence
- memory
- UI
- runtime
- consensus
- receipts
- replay state
- stale sessions

Only the Kernel can issue governed transitions.

Expand via 03_AUTHORITY_INVARIANT.md and 06_AUTHORITY_MODEL.md.

## 4. Threat Landscape

The binder documents nine threat domains, including cognitive, authority, evidence, continuity, execution, runtime, supply-chain, multi-agent bypass, and authority-creep meta-threats.

Expand via 13_THREAT_MODEL.md.

## 5. Multi-Vector Attack Analysis

The binder examines chained attack conditions such as replay combined with evidence tampering, authority spoofing combined with UI deception, continuity poisoning combined with proposal bias, and Kernel impersonation combined with session hijacking.

Expand via 14_MULTIVECTOR_ATTACK_ANALYSIS.md.

## 6. Verification Evidence

The September 30, 2026 Kernel diligence checkpoint completed with exit code 0 on a clean clone tracking origin/main. The documented suite includes authority, denial, replay, tamper, recovery, constitutional, COMA, circuit-breaker, and Synapse checks.

Expand via 17_VERIFICATION.md.

## 7. Chromium Edition

The Chromium Edition is architecturally integrated at the documented boundary, while x86-64 build, boot, runtime, and verified-boot evidence remain pending.

Expand via 20_CHROMIUM_EDITION.md.

## 8. Governance Implications

The architecture provides:

- canonical authority
- governed continuity
- deterministic recovery
- replay-resistant receipt mechanisms
- constitutional constraints
- bounded evidence
- dual-substrate / quad-engine separation

These are architectural properties and design claims to be evaluated against the cited implementation evidence.

## Current architecture baseline

This document is part of the current Convertible Cranium documentation set. The canonical architecture is Dual-Substrate / Quad-Engine: Cranium AI, Synapse, Governance Review Juror One, and Governance Review Juror Two. The jurors have deliberately different review mandates and processes and neither issues authority.

Commander OS is the operational control surface. Cranium Listener is untrusted ingress. Miracle Memory provides governed continuity. Circuit Breaker / COMA provides cross-cutting runtime containment and recovery. The Convertible Cranium Kernel remains the sole canonical authority source.

The former Eight-Plane and Dual-Engine descriptions are historical framing only and must not be read as the current governance model.
