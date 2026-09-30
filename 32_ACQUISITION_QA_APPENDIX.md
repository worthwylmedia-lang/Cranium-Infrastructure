# Acquisition Q&A Appendix

Authority-Bound • Dual-Engine • Governance Substrate

This appendix answers questions an external reviewer, OS architect, or governance evaluator is likely to ask. It clarifies the invariant, architecture, evidence boundaries, provenance, and readiness posture.

## Canonical Authority & Kernel Questions

### Q1 — What is the canonical authority implementation?

The canonical authority implementation is the Convertible Cranium Kernel, pinned at:

e36bdba2fe0a448473f94250920e751c95e1d3e0

This is the September 30, 2026 verified checkpoint.

Expand via 06_AUTHORITY_MODEL.md and 24_KERNEL.md.

### Q2 — Can cognition, evidence, memory, UI, runtime, or consensus create authority?

No. The Canonical Authority Invariant states that no combination of non-authoritative signals may synthesize canonical authority.

Expand via 03_AUTHORITY_INVARIANT.md.

### Q3 — How does the invariant prevent emergent authority?

Only the Kernel can issue governed authority transitions. Other components may propose, evaluate, constrain, execute, remember, contain, or prove, but they do not authorize.

Expand via 12_AUTHORITY_FLOW.md.

## Verification & Evidence Questions

### Q4 — What is the strongest current evidence?

The September 30, 2026 Kernel verification suite completed with exit code 0 on a clean clone tracking origin/main, including authority, denial, replay, tamper, recovery, constitutional, COMA, circuit-breaker, and Synapse checks.

Expand via 17_VERIFICATION.md.

### Q5 — What evidence is pending?

The Chromium Edition remains pending for:
- x86-64 ChromiumOS build
- boot evidence
- runtime validation
- verified-boot evidence

These states are not represented as completed.

Expand via 20_CHROMIUM_EDITION.md.

## Architecture & Threat Questions

### Q6 — How does Cranium differ from ordinary agent frameworks?

The governed path separates cognition from authority: cognition proposes, evidence informs, a governed request reaches the Kernel, the Kernel decides, execution obeys, and the transition produces a receipt.

Expand via 05_ARCHITECTURE.md and 12_AUTHORITY_FLOW.md.

### Q7 — What threats does Cranium address?

The binder documents a nine-domain threat model and multi-vector attack analysis mapped to the architecture and authority invariant.

Expand via 13_THREAT_MODEL.md and 14_MULTIVECTOR_ATTACK_ANALYSIS.md.

## IP, Provenance, Migration & Readiness

### Q8 — What is the IP boundary?

Cranium is positioned as a governance substrate, not a model, agent, or provider product. Commander OS is the operational/commercial surface; the Kernel is the canonical governance surface.

Expand via 19_IP_AND_PRODUCT_BOUNDARY.md.

### Q9 — How is provenance preserved?

The legacy engineering ecosystem remains intact as historical lineage while the acquisition-facing repository is curated as a clean diligence surface.

Expand via 18_DILIGENCE.md and 08_MIGRATION.md.

### Q10 — What is the migration path?

clean surface → secret sweep → structural gate → curated construction → Kernel reconciliation → Chromium evidence gate → authenticated migration → provenance preservation

Expand via 08_MIGRATION.md.

### Q11 — Is Cranium ready for external diligence?

The binder is structured for external diligence at the governance-substrate and architecture level. The ChromiumOS build, boot, runtime, and verified-boot evidence gate remains pending.

Expand via 09_ACQUISITION_READINESS_CHAPTER.md.

## Evidence Posture

PASS means verified evidence exists for the stated scope. PENDING means the work or evidence gate remains open. NOT CLAIMED means the binder deliberately makes no unsupported assertion.
