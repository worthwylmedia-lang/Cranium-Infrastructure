# Convertible Cranium — Acquisition Binder

## Governed-Intelligence Substrate

Convertible Cranium is documented here as an authority-bound, dual-engine governance substrate. This binder is an acquisition-facing evidence index, not a second authority implementation.

> Cognition proposes. Authority decides. Execution obeys. Continuity is governed. Recovery is deterministic.

## Claim status at a glance

| Claim | Evidence path | Status |
|---|---|---|
| Canonical Kernel evidence is standardized on clean commit `0d0ae41f78e3f23da073390285d401c4a215dc6a` | KERNEL_PIN, evidence/verification-records/KERNEL_VERIFICATION_2026-09-30.md | Verified checkpoint |
| Kernel clean-clone verification completed with documented commands | KERNEL_PIN, 17_VERIFICATION.md | Self-attested executable checkpoint |
| Wave V security suite records 17 hostile attacks, 9 controls/checks, and 3 pending evidence gates | evidence/WAVE_V_BURN_RESULTS_2026-09-30.md | Verified on the standardized clean checkout; 3 environment gates pending |
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

The standardized Kernel evidence revision is `0d0ae41f78e3f23da073390285d401c4a215dc6a`, a clean commit created after the Wave V classification/proof-reporting corrections. The prior `e36bdba...` checkpoint is historical and is not the revision used for the current Wave V ledger. The recorded command sequence is:

    npm ci
    npm run verify
    npm run verify:denial-semantics

Recorded local environment: Node v24.18.0, clean working tree at the standardized revision, Android/arm64 Termux, verification date 2026-09-30, exit code 0. The target Chromium Edition platform remains native x86-64; Android/arm64 is a development/verification environment, not the target OS runtime.

This is a self-attested executable checkpoint, not an independent third-party audit. A stranger must have access to the exact Kernel revision and its dependency lockfile to reproduce it. The current acquisition binder is public, while the historical Kernel path may be inaccessible to a reviewer using a different authenticated account. That access/provenance boundary is therefore a diligence item, not a hidden assumption.

The full output is retained in the verification record rather than summarized as a bare “pass.” The reviewer should independently rerun the commands and compare the observed output, runtime, lockfile, and repository revision.

## Attack and test ledger

The canonical Wave V ledger is `evidence/TEST_AND_ATTACK_LEDGER_2026-09-30.md`. It separates **17 hostile attack conditions** from **9 controls/checks** and **3 pending runtime gates**. The 17/9 split is classification, not a claim that every control is an attack. V3-A and V4-A retain their deterministic workload counts inside one ledger row each.

The acquisition stress suite remains a manifest until each case has a real executable binding and captured evidence.

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

## Public Front Door / Production System of Record

This repository is the primary public architecture and acquisition binder for Convertible Cranium. It is intentionally a **curated public front door, not a second production implementation**.

The authoritative production system remains under [`worthwyl2022-cloud`](https://github.com/worthwyl2022-cloud). This account explains and directs; the production account implements and proves.

### Production mapping

| Public architecture concept | Authoritative production surface |
|---|---|
| Canonical authority | [`cranium-kernel`](https://github.com/worthwyl2022-cloud/cranium-kernel) |
| Evidence / attestation | [`cranium-synapse`](https://github.com/worthwyl2022-cloud/cranium-synapse) |
| Cognitive proposal | [`cranium-ai`](https://github.com/worthwyl2022-cloud/cranium-ai) |
| Commander / operator surface | [`cranium-ultra-platform`](https://github.com/worthwyl2022-cloud/cranium-ultra-platform) |
| Verification / diligence | [`cranium-diligence-workbench`](https://github.com/worthwyl2022-cloud/cranium-diligence-workbench) |
| Appliance delivery | [`cranium-boot-drive`](https://github.com/worthwyl2022-cloud/cranium-boot-drive) |
| Acquisition demonstration | [`cranium-acquisition-demo-drive`](https://github.com/worthwyl2022-cloud/cranium-acquisition-demo-drive) |
| Historical lineage | [`cranium-archive`](https://github.com/worthwyl2022-cloud/cranium-archive) |

## Cranium Commander Boundary

**Cranium Commander is the operational control surface, not the canonical authority source.**

Commander may present system state, construct proposals, orchestrate governed workflows, submit authority requests, and participate in runtime safety and continuity. It does not create canonical authority, replace the Kernel, redefine constitutional truth, or become an independent system of record.

The production Commander/operator implementation is mapped through `worthwyl2022-cloud/cranium-ultra-platform`.

The governing distinction is:

> **Cognition may come from anywhere. Authority comes only through Cranium.**

## Public Evidence Status

This binder distinguishes **Verified**, **Self-attested**, **Pending**, and **Not claimed** material. Public architecture descriptions are not treated as independent verification merely because they are documented here.

Private credentials, keys, sensitive media, private contracts, and unsupported production/security claims remain outside this public surface.
