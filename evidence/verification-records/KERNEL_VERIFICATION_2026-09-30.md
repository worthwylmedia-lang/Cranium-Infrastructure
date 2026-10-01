# Kernel Verification Record — 2026-09-30

## Verified Revision

Repository: `cranium-kernel`
Branch: `main`
Verified SHA: `e36bdba2fe0a448473f94250920e751c95e1d3e0`
Environment: clean clone tracking `origin/main`
Runtime: Node v24.18.0, npm 11.19.1
package-lock.json SHA-256: `cf38054cc1326a816c80fdb92b63209242b9cde2dd9cae94002b9aa40373f199`

## Commands

`npm ci && npm run verify && npm run verify:denial-semantics`

Observed exit code: `0`

## Recorded Results

- npm install: 71 packages, 72 audited, 0 vulnerabilities.
- Lint passed.
- Build passed.
- Command Law passed, including foreign-issuer and namespace-bypass blocking and fail-closed behavior.
- Execution Gate passed, including law, capability, receipt, result, replay, expiry, scope, and foreign-issuer checks.
- Trust chain passed.
- Key Manager passed.
- Miracle Memory: 30 passed, 0 failed.
- Synapse integration passed, including signed attestation, replay denial, receipt-chain integrity, Ed25519 tamper checks, and rogue-key checks.
- SynapseController Phase 3 passed.
- Atomic recovery passed.
- Durable authority passed.
- Lifecycle matrix passed.
- Conformance: 8/8.
- Constitution passed: 8 directives, 7 engine proofs, contract alignment.
- Constitution runtime passed: version 1.0.0, 8 directives, 10 invariants.
- COMA passed.
- Cognitive subconscious runtime passed.
- Proofing passed.
- Session circuit breaker passed, including critical trip, fail-closed fencing, rollback, generation fencing, half-open recovery, snapshot integrity, and tamper rejection.
- Synapse adapter passed.
- Denial semantics passed, including quarantine, replay blocking, and evidence-tamper blocking.
- Enterprise integration passed.
- Distributed session passed, including stale-fence rejection.
- Production-readiness checks passed with environment-specific warnings concerning local PostgreSQL TLS and Redis transport. Production deployments require appropriate managed/private encryption configuration.

## Acquisition Stress Suite

The verification record enumerated 14 acquisition stress tests with suite digest `8cdc6a1be711553e2de8b44a280e1d30a1fc3bc652da6520723de56d4106977e`.

The execution standard requires real executable evidence tied to exact revision, runtime, configuration, and outputs. The existence of the suite is not treated as proof that an unexecuted future deployment has passed it.

## Command-Law Digest

Recorded digest: `84daf39234d6fd9c962da9772309a3d26b343d5fa15be08e09a27321bc2a1d05`

## Boundary

This is a diligence checkpoint for the identified Kernel revision. It is not a production certification, HSM/KMS certification, ChromiumOS runtime certification, or guarantee about future revisions or deployments.
