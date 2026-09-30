# Cranium Structural Validation Matrix

**Infrastructure Ecosystem • Authority-Bound • Dual-Engine • Governance Substrate**

This matrix is the pre-migration acceptance gate for the clean acquisition surface. It validates structural completeness, authority coherence, evidence integrity, provenance, repository hygiene, and migration readiness.

## Status Model

- **PASS** — requirement is satisfied by documentary or executable evidence.
- **PENDING** — evidence is intentionally incomplete and the limitation is explicitly documented.
- **FAIL** — the requirement is violated or evidence contradicts the requirement.

**Migration rule:** no FAIL is permitted. PENDING is permitted only when the missing evidence is explicitly bounded and does not get represented as verified.

## 1. Category and Invariant Integrity

| Validation Item | Requirement | Evidence | Status |
|---|---|---|---|
| Category Definition | Category and boundaries are explicit | `CATEGORY_DEFINITION.md` | PENDING |
| Category Research | Research is separated from legal conclusions | `CATEGORY_RESEARCH_PAPER.md` | PENDING |
| Authority Invariant | Formal, testable, corpus-wide invariant exists | `03_AUTHORITY_INVARIANT.md` | PENDING |
| Invariant Propagation | Core corpus references the invariant consistently | Corpus scan | PENDING |
| Invariant Enforcement | No subsystem contradicts the invariant | Corpus contradiction scan | PENDING |

## 2. Architectural Completeness

| Validation Item | Requirement | Evidence | Status |
|---|---|---|---|
| Eight-Plane Architecture | All eight planes and boundaries documented | `ARCHITECTURE.md` | PENDING |
| Subsystems | Commander, AI, Synapse, Kernel, Memory, COMA documented | Subsystem specifications | PENDING |
| Constitution | Durable directives and invariants documented | `CONSTITUTION.md` | PENDING |
| Authority Flow | Full governed transition path documented | `AUTHORITY_FLOW.md` | PENDING |
| Governed Transition | Consequential operation traced end to end | `GOVERNED_TRANSITION_EXAMPLE.md` | PENDING |

## 3. Authority Boundary

| Validation Item | Requirement | Evidence | Status |
|---|---|---|---|
| Canonical Source | Canonical authority resolves only to Kernel | `AUTHORITY_MODEL.md`, `KERNEL.md`, `KERNEL_PIN` | PENDING |
| Non-Emergence | No non-authoritative signal can synthesize authority | `03_AUTHORITY_INVARIANT.md` + tests | PENDING |
| Receipt Integrity | Receipts are integrity-checked and replay-resistant | Verification record | PENDING |
| Denial Semantics | Denial is explicit and testable | Verification record | PENDING |
| Stale Sessions | Stale authority cannot be inherited | Session verification | PENDING |
| Cross-Plane Composition | Valid signals cannot combine into a Kernel bypass | Multi-vector analysis + executable evidence | PENDING |

## 4. Threat and Attack Surface

| Validation Item | Requirement | Evidence | Status |
|---|---|---|---|
| Threat Domains | Nine threat domains mapped across the eight architectural planes and external boundaries | `THREAT_MODEL.md` | PENDING |
| Multi-Vector Analysis | Chained cross-plane attacks documented | `MULTIVECTORATTACK_ANALYSIS.md` | PENDING |
| Attack-to-Control Mapping | Threats identify applicable controls or evidence gaps | Threat/control matrix | PENDING |
| Invariant Stress Tests | Authority-violation paths are explicitly tested | Verification corpus | PENDING |
| Replay and Tamper Tests | Replay, tamper, rogue-key, and stale-state defenses have evidence | Verification record | PENDING |

## 5. Verification and Evidence

| Validation Item | Requirement | Evidence | Status |
|---|---|---|---|
| Verification Contract | Commands and acceptance boundaries are documented | `VERIFICATION.md` | PENDING |
| Kernel Checkpoint | September 30 clean-clone verification preserved | Kernel verification record | PENDING |
| Executable Evidence | Denial, replay, attestation, recovery, and constitutional checks recorded | Verification record | PENDING |
| Evidence Integrity | Revision, digest, command, runtime, and limitation data are preserved | Evidence records | PENDING |
| ChromiumOS Boundary | Image build/boot/runtime state is not overstated | `CHROMIUM_EDITION.md` | PENDING |

## 6. IP, Boundary, and Provenance

| Validation Item | Requirement | Evidence | Status |
|---|---|---|---|
| IP/Product Boundary | Product surface and retained substrate are distinguished | `IP_AND_PRODUCT_BOUNDARY.md` | PENDING |
| Provenance | Engineering evolution and research lineage are preserved | `provenance/` | PENDING |
| Historical Repositories | Legacy account remains available for deeper provenance | Audit evidence | PENDING |
| Acquisition Surface | Clean repository is curated rather than a raw mirror | Binder structure | PENDING |
| Credential Separation | New-account credentials are not mixed with legacy credentials | Authentication state | PENDING |

## 7. Repository Structure and Hygiene

| Validation Item | Requirement | Evidence | Status |
|---|---|---|---|
| Front Matter | Executive → Introduction → Category → Research → Invariant ordering is represented | Numbered binder files | PENDING |
| Directory Structure | Subsystems, evidence, provenance, and demos are complete | Filesystem manifest | PENDING |
| Evidence Directory | Verification records are intact and traceable | `evidence/verification-records/` | PENDING |
| Chromium Edition | Positioned after core authority, threat, and verification material | Binder structure | PENDING |
| No Private Assets | No private voice, credentials, tokens, secrets, or machine-local artifacts | Secret/private sweep | PENDING |
| No Accidental Build State | Generated artifacts and unrelated work are excluded unless explicitly required | Git diff + ignore policy | PENDING |

## 8. Migration Readiness

| Validation Item | Requirement | Evidence | Status |
|---|---|---|---|
| Surface Complete | All required acquisition documents present | Filesystem manifest | PENDING |
| Secret Sweep | No credentials, tokens, private assets, or sensitive logs | Sweep output | PENDING |
| Claim Boundary | No unsupported production, certification, legal, or affiliation claims | Claim scan | PENDING |
| Clean Reconstruction | Surface can be reconstructed without undocumented private state | Reconstruction test | PENDING |
| New Account Empty | Destination repository is confirmed empty before first push | GitHub remote inspection | PASS |
| Authentication | New account authentication is established separately | GitHub auth evidence | PENDING |
| Push Scope | Only curated acquisition surface will be pushed | Migration manifest | PENDING |

## Final Acceptance Questions

The migration gate must answer **NO** to every prohibited authority path:

1. Can AI output create authority without Kernel issuance?
2. Can Synapse assessment create authority?
3. Can memory create authority?
4. Can Commander UI state create authority?
5. Can multiple agents collectively create authority?
6. Can a replayed receipt create authority?
7. Can tampered evidence create authority?
8. Can compromised runtime state create authority?
9. Can a stale session inherit authority?
10. Can an attacker combine individually valid signals to bypass the Kernel?

Each answer must be supported by executable evidence where the implementation exposes that path.
