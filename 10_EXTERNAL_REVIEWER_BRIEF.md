## Reviewer Focus
1. **Authority invariant:** trace consequential transitions to the canonical Kernel boundary.
2. **Kernel canonicality:** reconcile the current Kernel revision and downstream pins.
3. **Replay/tamper resistance:** inspect signatures, receipts, replay fences, evidence integrity, and denials.
4. **Subsystem boundaries:** confirm Commander, AI, Synapse, Memory, COMA, Constitution, and receipts do not create authority by composition.
5. **ChromiumOS runtime:** treat as pending until an x86-64 image is built, booted, and validated.
6. **Provenance:** distinguish current verified evidence from historical lineage.
7. **IP/product boundary:** review offered product surface versus retained infrastructure/IP.
## Evidence Posture
- **PASS** means the gate has supporting evidence in the identified record.
- **PENDING** means required evidence is not yet available.
- **NOT CLAIMED** means the binder intentionally does not assert a stronger assurance level.
A subsystem PASS is not whole-product certification. Documented ChromiumOS architecture is not proof of a bootable or production-certified OS image.
## Suggested Diligence Sequence
Start with the invariant and architecture. Trace one governed transition end to end. Reconcile the Kernel revision and executable verification record. Inspect threat/defense mappings and denial semantics. Review IP/provenance. Finally, validate the Chromium Edition directly when pending build/runtime artifacts exist.
The purpose is traceability, not persuasion. Each material claim should lead to a repository, revision, artifact, test, or runtime observation.
