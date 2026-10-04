# Reviewer Interview Packet

For acquisition teams, OS architects, governance evaluators, and technical diligence reviewers.

This packet provides structured prompts for evaluating Cranium's architecture, authority model, evidence, provenance, and readiness without substituting reviewer judgment for documented evidence.

## Section 1 — Authority Boundary

- Evaluate the Canonical Authority Invariant.
- Confirm that Kernel-issued authority is the only canonical authority source.
- Test non-emergence across cognition, evidence, memory, UI, runtime, and consensus.
- Trace a governed transition from request through receipt.

Expand via 03_AUTHORITY_INVARIANT.md, 06_AUTHORITY_MODEL.md, and 12_AUTHORITY_FLOW.md.

## Section 2 — Architecture

- Review the dual-substrate / quad-engine architecture.
- Validate subsystem boundaries.
- Confirm separation between cognition and authority.
- Identify any path by which a non-authoritative component could bypass the Kernel.

Expand via 05_ARCHITECTURE.md.

## Section 3 — Threat & Attack Surface

- Review the nine-domain threat model.
- Review the multi-vector attack analysis.
- Validate attack → defense mapping.
- Test whether the invariant survives chained failure conditions.

Expand via 13_THREAT_MODEL.md and 14_MULTIVECTOR_ATTACK_ANALYSIS.md.

## Section 4 — Verification

- Review Kernel verification evidence.
- Validate denial semantics.
- Validate replay and tamper controls.
- Validate recovery and circuit-breaker behavior.
- Confirm evidence provenance and exact revision references.

Expand via 17_VERIFICATION.md and 18_DILIGENCE.md.

## Section 5 — Chromium Edition

- Review the documented OS integration boundary.
- Confirm that architecture and integration artifacts are distinct from boot/runtime evidence.
- Validate the pending evidence gate.
- Examine provenance from source revision to eventual image artifact.

Expand via 20_CHROMIUM_EDITION.md.

## Section 6 — IP & Provenance

- Review the IP and product boundary.
- Validate historical lineage preservation.
- Confirm that migration did not silently alter canonical source status.
- Identify any third-party or private material requiring separate diligence.

Expand via 19_IP_AND_PRODUCT_BOUNDARY.md and 08_MIGRATION.md.

## Section 7 — Migration & Readiness

- Review the migration chapter and structural gates.
- Validate the secret/private-material sweep.
- Reconcile the Kernel pin.
- Confirm the ChromiumOS runtime evidence gate remains open until independently evidenced.

Expand via 08_MIGRATION.md and 09_ACQUISITION_READINESS_CHAPTER.md.

## Reviewer Acceptance Principle

A reviewer should distinguish documented architecture, executable verification, pending evidence, and unclaimed assertions. No document should be treated as proof of an implementation boundary that has not been independently evidenced.

## Current architecture baseline

This document is part of the current Convertible Cranium documentation set. The canonical architecture is Dual-Substrate / Quad-Engine: Cranium AI, Synapse, Governance Review Juror One, and Governance Review Juror Two. The jurors have deliberately different review mandates and processes and neither issues authority.

Commander OS is the operational control surface. Cranium Listener is untrusted ingress. Miracle Memory provides governed continuity. Circuit Breaker / COMA provides cross-cutting runtime containment and recovery. The Convertible Cranium Kernel remains the sole canonical authority source.

The former Eight-Plane and Dual-Engine descriptions are historical framing only and must not be read as the current governance model.
