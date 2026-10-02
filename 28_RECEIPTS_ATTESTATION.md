# Receipts and Attestation

Receipts provide verifiable records of governed transitions. Attestation binds relevant evidence to an auditable transition.

Integrity, signatures, replay resistance, scope, and provenance are part of the verification boundary. A receipt is not an independent authority source.

## Current architecture position

This subsystem participates in the current Dual-Substrate / Quad-Engine architecture. It does not create canonical authority independently. The Convertible Cranium Kernel remains the sole canonical authority source; Governance Review Juror One and Governance Review Juror Two are distinct review paths, not authority issuers.
