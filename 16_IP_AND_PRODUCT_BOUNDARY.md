# Commander OS — Package Boundary (Stabilize)

**Status:** Commercial / diligence boundary document
**Product name:** Convertible Cranium Commander OS (Cranium OS operator surface)
**Repository:** `worthwyl2022-cloud/cranium-ultra-platform`
**Primary path:** `projects/cranium-os/`
**Document date:** 2026-09-30
**Owner:** Wyl Mathes · WorthWyl Media

> Cognition may come from anywhere. Authority comes only through Cranium.

This document defines what **is** and **is not** included if Commander OS is licensed or sold as a standalone package for runway or product transfer. It is an engineering boundary, not a legal opinion or executed agreement.

---

## 1. In scope (Commander OS package)

| Asset | Location | Role |
|-------|----------|------|
| Operator UI / cognitive workspace | `projects/cranium-os/` | Human/agent operator surface |
| Substrate Terminal | `projects/cranium-os/src/ui/...` | Intention injection / trace display |
| Canonical Ledger **view** | OS UI components | Display of transitions; not the durable authority store |
| Authority Dashboard **view** | OS UI components | Display of status; not the grant engine |
| AuthorityBridge (client) | `projects/cranium-os/src/os/AuthorityBridge.ts` | Fail-closed adapter; requires Kernel endpoint |
| OS tests | `projects/cranium-os/tests/` | Bridge / UI-level checks |
| Ultra monorepo scripts that only verify OS | `package.json` → `verify:os` | Build/typecheck/test for OS |

**Behavioral contract of the OS client**

- `AuthorityBridge.submit()` returns `UNAVAILABLE` / `KERNEL_ENDPOINT_REQUIRED` until an authenticated Kernel endpoint is configured.
- No browser-local evaluator, reducer, receipt issuer, or authority ledger.
- `CANONICAL_AUTHORITY_SOURCE = 'cranium-kernel'`.

---

## 2. Out of scope (retained unless separately priced)

| Asset | Location / note | Why retained |
|-------|-----------------|--------------|
| **Cranium Kernel** | `worthwyl2022-cloud/cranium-kernel` | Sole canonical authority issuer |
| KeyManager / key custody | Kernel `src/governance/KeyManager.ts` | Signing identity lifecycle |
| Artifact lifecycle / receipts | Kernel governance | Authority-bound artifacts |
| Synapse controller / attestation runtime | Kernel (+ `cranium-synapse` contract) | Evidence plane, not OS |
| Miracle Memory | Kernel memory subsystem | Durable authority-adjacent memory |
| COMA / cognitive subconscious | Kernel | Containment / quarantine |
| Constitution / Canon / protocol | Kernel `docs/` + `CRANIUM_CORE_CANON_V1.md` | Constitutional IP |
| Superseded hardened core | `projects/cranium-core-hardened/` | Historical / adversarial harness only — **not** sold as production Core |
| Boot / Chromium Edition / ISO | `cranium-boot-drive`, acquisition demo drive, GitLab artifacts | Delivery appliances |
| Cranium AI product apps | `cranium-ai`, `Convertible-Cranium-ai-v-2.0` | Separate product tips |
| Private Wyl voice / private payloads | Not in this repo’s public OS path | Private media IP |
| Provider gateways | `cranium-provider-integrations` | Proposal plane |
| WorthWyl Forge / media clients | Separate repos | Non-canonical clients |

**Rule:** Selling or licensing Commander OS does **not** transfer Kernel, Canon, constitution, Synapse runtime, or boot-image IP unless an explicit written schedule says so and prices it.

---

## 3. Authority relationship

```text
Commander OS  →  constructs AuthorityTransitionRequest
             →  AuthorityBridge (fail-closed client)
             →  cranium-kernel (sole grant / deny / receipt)
```

| Layer | May | May not |
|-------|-----|--------|
| Commander OS | Propose, display, test, operate UX | Grant authority, commit canonical state, issue receipts |
| cranium-kernel | Evaluate, grant/deny, journal, receipt | Be replaced by OS localStorage or UI state |

Hardened core under this monorepo is **superseded reference / adversarial harness**. See `projects/cranium-core-hardened/docs/AUTHORITY_SOURCE.md`.

---

## 4. Kernel pin (machine-readable)

File: `KERNEL_PIN` (repo root)

| Field | Value |
|-------|--------|
| Current verified Kernel diligence pin | `e36bdba2fe0a448473f94250920e751c95e1d3e0` (verified 2026-09-30) |
| Historical Phase 1–3 reproducibility gate | `c2bd6d3` / `c2bd6d38a71f1ae124beec73df68b8af91a23bc0` |
| Historical Kernel `main` tip (Canon V1 squash lineage) | `482b9c54a80f0894e523cb94c77fa85d3f62c264` |

OS integrations and diligence should treat **`cranium-kernel` on GitHub** as source of truth. Refresh `KERNEL_PIN` when the OS package is cut for a buyer so the pin matches the negotiated Kernel relationship (retained / licensed / excluded).

---

## 5. How to run (demo tip)

```bash
cd projects/cranium-os
npm ci
npm run dev
# optional: npm test / typecheck / build via monorepo verify:os
```

From monorepo root:

```bash
npm run verify:os
```

Expected diligence story for a demo: operator UI loads; authority submission without Kernel endpoint remains **unavailable**; no local grant.

---

## 6. Non-claims

Commander OS package boundary does **not** claim:

- HSM/KMS or production secret custody
- Independent security audit or formal verification
- That OS-alone is a complete governed-authority product without a Kernel
- GitHub-hosted CI green as a substitute for local/VPS verification
- Transfer of trademarks, company equity, or Kernel IP by implication

---

## 7. Suggested commercial schedules (labels only)

Use these names in any future term sheet; counsel must draft the actual agreement.

| Schedule | Meaning |
|----------|--------|
| **Schedule A — OS** | `projects/cranium-os` + listed UI assets |
| **Schedule B — Retained IP** | Kernel, Canon, Synapse, Memory, boot, AI apps, voice |
| **Schedule C — Optional Kernel license** | Time-bounded or usage-bounded integration with seller-retained Kernel |
| **Schedule D — Excluded** | Hardened-core harness, private payloads, other repos |

Default posture for runway discussions: **Schedule A only**; B retained; C optional and priced; D excluded.

---

## 8. Diligence checklist (OS-only inbound)

- [ ] This boundary doc reviewed
- [ ] `AuthorityBridge.ts` inspected (fail-closed)
- [ ] `AUTHORITY_SOURCE.md` (hardened core demoted) reviewed
- [ ] `KERNEL_PIN` recorded
- [ ] Demo: OS runs; no local grant
- [ ] Written list of retained repos matches Section 2

---

## Canonical one-liner

> **Commander OS is the operator surface. Cranium Kernel is the authority. An OS-only package transfers the surface, not the throne.**
