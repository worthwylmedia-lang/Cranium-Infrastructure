## Acquisition Readiness Summary
Convertible Cranium is ready for external diligence review at the binder and governance-substrate level, with one material implementation boundary still open: actual ChromiumOS x86-64 build, boot, runtime validation, and verified-boot evidence.
The acquisition record distinguishes:
- **PASS:** supported by the identified documented/executable evidence.
- **PENDING:** the gate exists but required evidence has not yet been produced.
- **NOT CLAIMED:** a stronger assurance level is outside the evidence established here.
The ChromiumOS pending gate must remain visible until an actual image is built and runtime-validated. Documentation cannot substitute for boot evidence. Humanity has spent decades learning this and then repeatedly pretending otherwise.
## Acceptance Rule
External reviewers may treat this binder as a structured diligence corpus. Material claims should be independently validated against source repositories, revisions, artifacts, executable tests, and runtime behavior before transaction or technical-assurance reliance.

## Current architecture baseline

This document is part of the current Convertible Cranium documentation set. The canonical architecture is Dual-Substrate / Quad-Engine: Cranium AI, Synapse, Governance Review Juror One, and Governance Review Juror Two. The jurors have deliberately different review mandates and processes and neither issues authority.

Commander OS is the operational control surface. Cranium Listener is untrusted ingress. Miracle Memory provides governed continuity. Circuit Breaker / COMA provides cross-cutting runtime containment and recovery. The Convertible Cranium Kernel remains the sole canonical authority source.

The former Eight-Plane and Dual-Engine descriptions are historical framing only and must not be read as the current governance model.
