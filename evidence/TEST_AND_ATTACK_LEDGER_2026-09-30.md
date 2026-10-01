# Test and Attack Ledger — 2026-09-30

## Standard evidence revision

- Repository: `cranium-kernel`
- Standard revision: `0d0ae41f78e3f23da073390285d401c4a215dc6a`
- Runtime: Node v24.18.0
- Development/verification host: Android/arm64 Termux
- Target platform: native x86-64 ChromiumOS
- Wave V result: **26 PASS, 0 vulnerability findings, 3 pending**
- Classification: **17 hostile attacks + 9 controls/checks + 3 pending gates**

The classification is intentionally narrower than the raw PASS count. Positive controls, provenance/static checks, and structural fixtures are not described as attacks.

## Hostile attack conditions: 17

| ID | Type | Result | What was exercised | Boundary/result |
|---|---|---|---|---|
| V1-B | Hostile attack | PASS | Receipt signature forgery | Rejected as `SIGNATURE_INVALID` |
| V1-C | Hostile attack | PASS | Wrong-key receipt | Rejected as `SIGNATURE_INVALID` |
| V1-D | Hostile attack | PASS | Receipt payload tampering | Rejected as `SIGNATURE_INVALID` |
| V1-E | Hostile attack | PASS | Valid CORE signature using stolen trusted private key without canonical custody proof | Rejected as `CANONICAL_CUSTODY_PROOF_MISSING`; custody mitigation is process-local |
| V1-F | Hostile attack | PASS | Revoked Kernel key attempts signing through KeyManager | Rejected as `NO_SIGNING_KEY: CORE` |
| V2-B | Hostile attack | PASS | Constitution mutation | Constitutional state violation rejected |
| V2-C | Hostile attack | PASS | Missing/unsigned governance article | Constitutional state violation rejected |
| V2-D | Hostile attack | PASS | Disabled constitutional directive | Constitutional state violation rejected |
| V2-E | Hostile attack | PASS | Duplicate Constitution directive | Duplicate principle IDs rejected |
| V2-F | Hostile attack | PASS | Wrong-key Constitution signature | Rejected as `UNKNOWN_KEY_ID` |
| V2-G | Hostile attack | PASS | Signed-Constitution payload mutation | Trusted load succeeds; mutated payload rejected |
| V3-A | Hostile attack | PASS | Continuity contradiction flood | 1,500 deterministic hostile provisional writes; journal remained intact |
| V3-B | Hostile attack | PASS | Poisoned continuity | Quarantine forced weight to zero |
| V3-C | Hostile attack | PASS | Continuity snapshot corruption | Tampered snapshot rejected |
| V3-D | Hostile attack | PASS | Constitutional memory overwrite | Immutable constitutional atom rejected overwrite |
| V4-B | Hostile attack | PASS | Execution bypass while COMA is open | Execution rejected while session was `TRIPPED_OPEN` |
| V9-A | Hostile attack | PASS | Altered-message Ed25519 forgery | Native crypto verification failed closed |

## Controls and checks: 9

| ID | Type | Result | What it establishes | Boundary/result |
|---|---|---|---|---|
| V1-A | Control/check | PASS | Canonical Ed25519 happy path | Trusted CORE signature accepted |
| V1-G | Control/check | PASS | Canonical KeyManager custody proof | Canonical signature carried custody proof |
| V2-A | Control/check | PASS | Canonical Constitution baseline | All Prime Directives present and enforced |
| V4-A | Control/check | PASS | COMA recovery/containment | 25 deterministic trip/rollback/recovery cycles remained fenced |
| V5-A | Control/check | PASS | Chromium Kernel pin provenance | Pin is bound in ChromiumOS provenance; this is not a rootfs attack |
| V6-A | Control/check | PASS | Source-level authority boundary representation | Kernel/Command Law/AuthorityProxy/Memory/COMA references present |
| V7-A | Control/check | PASS | Adversarial multi-agent fixture boundary | Hostile-looking unanimous AI/Synapse/Commander data remained non-canonical; not an end-to-end hostile multi-agent runtime |
| V7-B | Control/check | PASS | Canonical issuer identity | Combined signals did not alter canonical issuer |
| V8-A | Control/check | PASS | Executable invariant representation | Prime Directives are represented as executable assertions |

## Pending evidence gates: 3

| ID | Type | Status | Why pending |
|---|---|---|---|
| V5-B | Runtime attack gate | PENDING | Live ChromiumOS verified-boot/rootfs poisoning requires native x86-64 image and boot environment; no simulation is substituted |
| V6-B | Runtime interaction gate | PENDING | Commander UI-language authority creep requires a running Commander session and scripted interaction; static inspection is insufficient |
| V8-B | Distributed runtime attack gate | PENDING | Kernel-unavailable behavior requires an external-process outage/fallback test; individual local fail-closed paths are not equivalent |

## Additional full verification battery

The same standardized revision also runs the broader Kernel verification chain: lint/build; Command Law; Command Execution Gate; trust chain; Key Manager; Miracle Memory; Synapse integration; key binding; Synapse Controller; atomic recovery; durable authority; lifecycle; conformance 8/8; Constitution; signed-Constitution loader; Constitution runtime; COMA; cognitive-subconscious; proofing; Session Circuit Breaker; Synapse adapter; denial semantics; enterprise integration; distributed session; production readiness; and acquisition-stress manifest generation. The acquisition stress suite remains a **manifest only**, not executed attack evidence.

## Constitution proof correction

The constitution checker contains 8 Prime Directives and checks 8 engine-proof markers. The prior output label `engine_proofs=7` was incorrect reporting. The standardized revision reports `engine_proofs=8`; the eighth marker is `assertConstitutionalTransition`.

## Security and deployment boundaries

V1-E demonstrates process-local canonical custody, not HSM/TPM custody, hardware-backed keys, or remote attestation.

Production readiness currently warns that local PostgreSQL TLS is disabled and local Redis is plaintext. Production requires PostgreSQL TLS (`CRANIUM_DB_SSL=true`) and encrypted Redis transport (`rediss://` or private-network encryption).

The Android/arm64 Termux host is a development/verification environment. The Chromium Edition target is native x86-64.

## Hosted x64 reproduction

GitHub documents `ubuntu-latest` as an x64 hosted runner for standard Linux jobs. A hosted run would improve environment diversity, but the connected GitHub account currently has no `worthwyl2022-cloud/cranium-kernel` repository, while the local remote still points there. No hosted result is claimed until the canonical Kernel repository is actually published/accessible at the intended remote.
