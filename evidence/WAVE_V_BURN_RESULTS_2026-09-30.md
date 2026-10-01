# Wave V Burn Results
Date: 2026-09-30
Repository under test: cranium-kernel
Revision under test: `0d0ae41f78e3f23da073390285d401c4a215dc6a`
Runtime: Node v24.18.0
Host: Android/arm64 Termux
Suite: `scripts/wave-v-burn-suite.mjs`

## Current executed result

**26 PASS conditions, 0 vulnerability findings, 3 evidence gates pending.**

The wording “0 vulnerabilities” is intentionally scoped: **no vulnerability was found among the 26 executed conditions at this exact revision.** This is not a claim that the substrate is invulnerable or that all attack classes are covered.

The current run is a fresh execution at the standardized clean revision `0d0ae41`, after the earlier Wave V revisions. The standardized revision includes the signed-Constitution gate, evidence classification, and corrected Constitution proof-count reporting. The original V1-E finding and mitigation remain part of the history; the current run re-executes V1-E and the signed-Constitution loader at the later revision.

## Revision chronology

- `60e0089` — added Wave V burn suite.
- `0daa563` — fixed V1-E by binding canonical CORE signatures to an in-process custody proof.
- `83bc556` — added the signed-Constitution load gate and its executable verification.
- `0d0ae41` — standardized the evidence classification as 17 hostile attacks + 9 controls/checks, corrected the Constitution proof count to 8, and retained the production-boundary exclusions.

The older `e36bdba...` clean-clone checkpoint is historical evidence only. It is not the standardized revision for this Wave V ledger.

## What the 26 executed conditions mean

The suite deliberately separates evidence categories. The standardized classification is:

- **17 hostile attack conditions:** V1-B, V1-C, V1-D, V1-E, V1-F, V2-B, V2-C, V2-D, V2-E, V2-F, V2-G, V3-A, V3-B, V3-C, V3-D, V4-B, V9-A.
- **9 controls/checks:** V1-A, V1-G, V2-A, V4-A, V5-A, V6-A, V7-A, V7-B, V8-A.
- **3 evidence gates pending:** V5-B, V6-B, V8-B.

This means **26 executed PASS conditions**, not 26 attacks. V3-A and V4-A retain their deterministic workload counts inside single conditions. V5-A is provenance evidence, V6-A is a static boundary check, and V7-A/V7-B are structural/fixture evidence rather than end-to-end hostile multi-agent runtime attacks.

## V1-E finding and limitation

The original test demonstrated that a valid Ed25519 CORE signature produced directly with the stolen private key could reach the generic trusted-key verification path. The mitigation added a separate process-custody proof to canonical KeyManager signatures. The re-attack now rejects the stolen-key signature with `CANONICAL_CUSTODY_PROOF_MISSING`.

The mitigation is **process-local**. It does not establish resistance against compromise of the running canonical process, extraction of the custody secret from that process, HSM/TPM-backed custody, or remote process attestation. Stronger production custody requires an external HSM/KMS, hardware-backed key, or attestation service.

## Deterministic attack workloads

- V3-A executes **1,500 deterministic hostile provisional writes**. It is not represented as 1,500 randomized attacks.
- V4-A executes **25 deterministic COMA trip/rollback/recovery cycles**. It is not represented as 25 independently randomized attack strategies.

The deterministic inputs are intentional so another reviewer can reproduce the same conditions exactly.

## Constitution proof-count correction

The Constitution checker contains 8 Prime Directives and checks 8 engine-proof markers. An earlier output label incorrectly said `engine_proofs=7`; the standardized revision reports `engine_proofs=8`. The eighth marker is `assertConstitutionalTransition`.

## Pending runtime evidence

1. **V5-B:** live ChromiumOS verified-boot rootfs poisoning. Requires a native x86-64 ChromiumOS image/boot environment.
2. **V6-B:** Commander UI-language authority creep under runtime interaction. Static source inspection is insufficient to establish this across runtime configurations.
3. **V8-B:** end-to-end distributed Kernel-unavailable fallback. Individual fail-closed paths exist, but the external-process outage/fallback behavior is not yet executed.

These remain pending and are not converted into passes.

## Attack-class coverage

The current evidence provides executed coverage for selected cognition/authority, continuity/memory, evidence/signature, replay/denial, and containment paths. UI-to-execution, distributed Kernel-unavailable fallback, live ChromiumOS verified boot, and genuine compromised-dependency scenarios remain incompletely evidenced. Agent laundering is represented by an adversarial fixture/structural check, not an end-to-end hostile multi-agent runtime.

The 14-case acquisition stress suite remains a **manifest only** until each case is bound to a real executable test with exact revision, runtime, configuration, and captured output. No synthetic pass result is claimed.

## Acquisition interpretation

**At `0d0ae41`, the project's own Wave V suite executed 26 test conditions on Android/arm64 Termux; all 26 passed, no vulnerability was found in those executed conditions, and 3 runtime-dependent evidence gates remain pending. Results are self-run and have not yet been independently reproduced.**

This record is a diligence checkpoint, not production certification, HSM/KMS certification, ChromiumOS runtime certification, or a guarantee about future revisions or deployments.
