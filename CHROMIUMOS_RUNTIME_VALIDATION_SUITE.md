# ChromiumOS Runtime Validation Suite

## Preconditions
- Exact image SHA256 recorded
- Source and manifest revisions recorded
- Kernel pin recorded
- Boot evidence captured
- Test environment recorded

## A. System identity
Confirm Convertible Cranium Chromium Edition, amd64 architecture, Commander loading, AI runtime availability, and required Wyl assets.

## B. Authority boundary
1. Submit a cognitive proposal and verify it is not authority.
2. Execute a valid governed Kernel transition.
3. Attempt foreign/malformed issuer paths.
4. Verify unauthorized transitions are rejected.
5. Verify UI state cannot manufacture authority.

## C. Evidence and continuity
Verify receipts/provenance, bounded Miracle Memory continuity, quarantine/contradiction handling, replay rejection, and Synapse's inability to issue canonical authority.

## D. Containment and recovery
Exercise Session Circuit Breaker under a defined critical condition. Verify containment, checkpoint rollback, governed recovery, and safe re-entry.

## E. User-facing behavior
Exercise Commander, AI interaction, Wyl presentation, explicit confirmation, consequential-action gating, and clear denial explanations.

## F. Offline/local behavior
Where applicable, disconnect external network access. Verify documented local functions remain available and missing external services fail closed.

## Evidence format
Every test records ID, image SHA256, environment, action, expected result, observed result, timestamp, logs/screenshots, and pass/fail disposition.

## Failure policy
A failed test stays failed. Code changes after failure require a new image and a new evidence run.

## Acceptance
Mandatory tests must pass against the exact recorded image, with evidence reproducible by an independent reviewer.
