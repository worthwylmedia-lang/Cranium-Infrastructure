# Convertible Cranium
## Attorney Review & Technical Diligence Binder

**Creator / intended personal IP owner:** William (Wyl) Mathes
**Purpose:** A navigable, evidence-linked record for intellectual-property counsel, technical reviewers, and prospective diligence partners.
**Evidence posture:** Architecture and implementation claims are separated from self-attested tests, pending validation, and legal questions.

> **Cognition may come from anywhere. Authority comes only through Convertible Cranium.**

Convertible Cranium is an authority-bound governance architecture designed to keep model-generated cognition separate from canonical authority. Models and application surfaces may propose; independently constituted governance substrates assess; the Convertible Cranium Kernel alone determines whether a governed authority transition is accepted.

This repository is an acquisition-facing documentation and evidence index. It is not a second implementation of the Kernel, a legal opinion, or a claim of independent certification.

---

## Start here

| If you are… | Begin with | Purpose |
|---|---|---|
| **IP attorney** | [Attorney Review Start Here](ATTORNEY_REVIEW_START_HERE.md) and [IP and Product Boundary](19_IP_AND_PRODUCT_BOUNDARY.md) | First-meeting brief, ownership questions, scope, exclusions, and retained components |
| **Attorney or diligence lead** | [Diligence Register](18_DILIGENCE.md) and [Implementation Status & Gap Register](40_IMPLEMENTATION_STATUS_AND_GAP_REGISTER.md) | Known gaps, non-claims, release gates, and evidence boundaries |
| **Technical reviewer** | [Architecture](05_ARCHITECTURE.md) | Canonical system path and component responsibilities |
| **Security reviewer** | [Threat Model](13_THREAT_MODEL.md) and [Attack Analysis](14_MULTIVECTOR_ATTACK_ANALYSIS.md) | Threat boundaries and mapped controls |
| **Verification reviewer** | [Verification](17_VERIFICATION.md) and [Evidence Ledger](evidence/TEST_AND_ATTACK_LEDGER_2026-09-30.md) | Recorded checks, test classifications, and open gates |
| **Chromium Edition reviewer** | [Chromium Edition](20_CHROMIUM_EDITION.md) | Staged integration versus boot/runtime evidence |
| **Executive reader** | [Executive Summary](00_EXECUTIVE_SUMMARY.md) | Concise explanation of the system and current limits |

## Architecture in one view

```text
UNTRUSTED INGRESS
        |
     LISTENER
        |
 ENGINE 1 · SYNAPSE
 proposals, context, evidence binding
        |
        +-------------------------------+
        |                               |
 ENGINE 2A · SUBSTRATE A          ENGINE 2B · SUBSTRATE B
 Constitutional Authority        Evidence Grounding
 "MAY WE?"                       "IS IT SO?"
        |                               |
        +---------------+---------------+
                        |
              ENGINE 3 · CRANIUM KERNEL
          canonical convergence and authority
                        |
               GOVERNED EXECUTION
                        |
               RECEIPT / PROOF / LINEAGE
```

**Boundary rules**

- Synapse proposes and binds context/evidence; it does not grant authority.
- Substrate A evaluates constitutional admissibility; Substrate B evaluates evidence grounding. Neither is authoritative.
- The Kernel is the sole canonical authority boundary.
- Commander OS is an operational interface, not the authority source.
- Miracle Memory provides governed continuity. Circuit Breaker / COMA provides cross-cutting containment and recovery.
- Convergence is not voting. If the required conditions do not converge, authority is not granted.

Cranium AI is a cognition/application surface, not an additional authority-path engine. Older Eight-Plane, Dual-Engine, or earlier juror-centered descriptions are historical framing and must not be mistaken for the current canonical path.

## Evidence status at a glance

| Area | Current documented posture | What remains open |
|---|---|---|
| Kernel verification | A project-recorded clean-checkout verification checkpoint is documented for commit `0d0ae41f78e3f23da073390285d401c4a215dc6a` | Independent reproduction by counsel/reviewer; confirm source access and revision |
| Wave V security ledger | Records 17 hostile attack conditions, 9 controls/checks, and 3 pending environment gates | Resolve and document the remaining gates |
| Custody boundary | Tested process-local custody behavior is documented | Do not represent it as HSM/KMS or hardware-backed custody |
| Signed Constitution | Project-recorded checks for tampering, foreign signer, and version mismatch are documented | Independent reproduction |
| Chromium Edition | Integration payloads and build/validation plans are documented | Native x86-64 image build, boot, runtime acceptance, and verified-boot evidence |
| Legal ownership | Intended personal ownership position and technical provenance are documented | Counsel must verify chain of title, contributors, assignments, licenses, and third-party obligations |
| Market / legal status | No unsupported claim is made | Market validation, patentability, novelty, and independent certification are not established by this binder |

**Evidence vocabulary:** *Verified* means supported by a named artifact or executable check; *self-attested* means recorded by project execution without independent third-party verification; *pending* means a named gate remains open; *not claimed* means the binder deliberately does not assert it.

## Repository and source boundaries

- **Public documentation front door:** [worthwylmedia-lang](https://github.com/worthwylmedia-lang)
- **Primary public binder:** [Cranium-Infrastructure](https://github.com/worthwylmedia-lang/Cranium-Infrastructure)
- **Engineering/source account:** [worthwyl2022-cloud](https://github.com/worthwyl2022-cloud)
- **Canonical Kernel repository:** [cranium-kernel](https://github.com/worthwyl2022-cloud/cranium-kernel)
- **Commander/operator implementation:** [cranium-ultra-platform](https://github.com/worthwyl2022-cloud/cranium-ultra-platform)
- **Acquisition demonstration:** [cranium-acquisition-demo-drive](https://github.com/worthwyl2022-cloud/cranium-acquisition-demo-drive)

The public binder and the engineering account serve different purposes. Repository history is relevant technical provenance, but GitHub account control and commit records alone do not establish legal title. Access, ownership, assignments, licenses, and contributor rights require separate diligence.

## Reviewer rule

Trace each material claim through:

**claim → document → repository + exact revision → command/test → artifact/output → evidence status**

A narrative description alone is not proof. A planned component is not a completed release. A project-run test is not an independent audit. A public repository is not, by itself, a chain-of-title instrument.

## Chromium Edition boundary

The Chromium Edition is documented as staged integration work until a supported native x86-64 build, boot, runtime acceptance, and verified-boot/rootfs evidence are captured. It must not be described as an official Google product or Google-supported build. ChromiumOS licensing, attribution, trademarks, and third-party obligations remain applicable.

## Ownership statement and legal caution

The project records **William (Wyl) Mathes** as the intended personal IP owner for the work covered by the acquisition record, subject to attorney verification of chain of title and any applicable prior assignments, third-party rights, licenses, employment/contractor obligations, or other legal encumbrances. No corporate ownership transfer should be inferred absent executed legal instruments.

This binder is prepared to support counsel's review. It does not manufacture, transfer, waive, register, or perfect any intellectual-property right, and it is not a substitute for legal advice.

---

**Truth above all.** The goal is not to make every status look green. The goal is to make every claim traceable, every gap visible, and every boundary understandable.
