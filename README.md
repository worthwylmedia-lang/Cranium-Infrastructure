# Convertible Cranium — Acquisition Binder

## Governed-Intelligence Substrate

Convertible Cranium is documented here as an authority-bound, dual-engine governance substrate. This binder is an acquisition-facing evidence index, not a second authority implementation.

> Cognition proposes. Authority decides. Execution obeys. Continuity is governed. Recovery is deterministic.

## Claim status at a glance

| Claim | Evidence path | Status |
|---|---|---|
| Canonical Kernel is pinned to main commit e36bdba2fe0a448473f94250920e751c95e1d3e0 | KERNEL_PIN, evidence/verification-records/KERNEL_VERIFICATION_2026-09-30.md | Verified checkpoint |
| Kernel clean-clone verification completed with documented commands | KERNEL_PIN, 17_VERIFICATION.md | Self-attested executable checkpoint |
| Wave V security suite blocks 25 tested attack conditions | evidence/WAVE_V_BURN_RESULTS_2026-09-30.md | Verified on tested checkout; 4 environment gates pending |
| Canonical custody hardening resists a valid CORE signature without custody proof | Kernel Wave V evidence | Verified on tested checkout; custody is process-local, not HSM |
| Signed Constitution loader rejects tampering, foreign signer, and version mismatch | Kernel signed-Constitution check | Verified on tested checkout |
| Chromium Edition integration payload/build scripts exist | 20_CHROMIUM_EDITION.md, root ChromiumOS plans | Verified as staged integration work |
| Bootable ChromiumOS image and native x86-64 runtime/verified-boot validation | CHROMIUMOS_BUILD_BOOT_PLAN.md, VERIFIED_BOOT_EVIDENCE_PLAN.md | Pending native x86-64 build environment |
| Market demand, security certification, legal novelty, or patentability | 18_DILIGENCE.md | Not claimed |
| Chain of title between legacy engineering account and acquisition surface | 19_IP_AND_PRODUCT_BOUNDARY.md, provenance/ | Diligence item, not silently assumed |

### Reviewer rule

Every material claim should be traceable as:

**claim → binder chapter → repository + commit → command/test → artifact/output → status**

A narrative statement without an executable artifact or explicit self-attestation/pending label is not treated as independent verification.

## Reproducibility checkpoint

The current Kernel checkpoint is e36bdba2fe0a448473f94250920e751c95e1d3e0 on origin/main. The recorded clean-clone command sequence is:

    npm ci
    npm run verify
    npm run verify:denial-semantics

Recorded environment: Node v24.18.0, clean clone, Android/arm64 Termux, verification date 2026-09-30, exit code 0.

This is a self-attested executable checkpoint, not an independent third-party audit. A stranger must have access to the exact Kernel revision and its dependency lockfile to reproduce it. The current acquisition binder is public, while the historical Kernel path may be inaccessible to a reviewer using a different authenticated account. That access/provenance boundary is therefore a diligence item, not a hidden assumption.

The full output is retained in the verification record rather than summarized as a bare “pass.” The reviewer should independently rerun the commands and compare the observed output, runtime, lockfile, and repository revision.

## Binder Map

00 Executive Summary
01 Binder Introduction
02 Category Definition and Boundary
03 Canonical Authority Invariant
04 Category Research Note
05 Eight-Plane Architecture
06 Authority Model
07 Structural Validation Matrix
08 Migration Chapter
09 Acquisition Readiness Chapter
10 External Reviewer Brief
11 Architecture Summary Sheet
12 Authority Flow
13 Threat Model
14 Multi-Vector Attack Analysis
15 Developer Mental Model
16 Governed Transition Example
17 Verification
18 Diligence
19 IP and Product Boundary
20 Chromium Edition
21 Commander OS
22 Cranium AI
23 Synapse
24 Kernel
25 Miracle Memory
26 Circuit Breaker / COMA
27 Constitution
28 Receipts / Attestation
29 Founder Foreword
30 Governed-Intelligence OS Abstract
31 Table of Contents
32 Acquisition Q&A Appendix
33 Reviewer Interview Packet
34 Governance Substrate Glossary
35 Binder Finalization Checklist
36 Governance Substrate Whitepaper
37 OS Architecture Poster
38 Human Utility Roadmap

### Supporting evidence and plans

- CHROMIUMOS_BUILD_BOOT_PLAN.md
- CHROMIUMOS_RUNTIME_VALIDATION_SUITE.md
- DEPLOYMENT_READINESS.md
- VERIFIED_BOOT_EVIDENCE_PLAN.md
- KERNEL_PIN
- evidence/
- provenance/
- demos/

## Canonical Authority

The binder does not create a second authority implementation. Canonical authority remains the separately maintained Convertible Cranium Kernel.

## Chromium Edition boundary

**Status: plan/integration payload only.** A bootable ChromiumOS image, native x86-64 build, runtime acceptance, and verified-boot/rootfs evidence are not claimed here until those gates execute on supported native build infrastructure.

The Chromium Edition must not be presented as an official Google product or Google-supported build. ChromiumOS licensing, attribution, trademarks, and third-party obligations remain applicable.

## Ownership and provenance

The acquisition surface is curated from work spanning the current acquisition account and the legacy engineering account. This binder preserves that distinction rather than pretending the account boundary does not exist. Chain-of-title and repository access are diligence items.

Private credentials, private voice assets, unsupported production claims, and unrelated legacy material do not belong in this binder.

## Evidence posture

This binder intentionally distinguishes:

- **Verified:** backed by an executable test, artifact, or reproducible repository state.
- **Self-attested:** recorded by the project from its own execution, without independent third-party verification.
- **Pending:** blocked by an identified environment, deployment, or review gate.
- **Not claimed:** explicitly outside the evidence established here.

No claim of invulnerability, certification, independent security audit, market validation, or completed ChromiumOS production release is made by this binder.
