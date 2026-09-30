# Wave V Burn Results
Date: 2026-09-30
Repository under test: cranium-kernel
Commit under test: 1dff8d32fc4585c4ad8192c806ef29ef72579907
Runtime: Node v24.18.0
Host: Android/arm64 Termux
Suite: scripts/wave-v-burn-suite.mjs

## Result
PASS: 23
VULNERABILITY_FOUND: 1
EVIDENCE_PENDING: 4

The suite used executable attacks and local fixtures. Pending environment gates were not converted into passes.

## Finding V1-E
A holder of a valid trusted CORE private key can create a cryptographically valid SignedPayload that the generic TrustedKeyRegistry accepts. The registry validates key identity, role, validity, revocation and Ed25519 signature, but has no process-attestation or canonical-execution-path binding.

This is an architectural limitation of signature verification, not proof that a forged signer can directly commit Kernel durable authority through KernelAuthorityProxy. The existing authority path separately enforces canonical issuer and Command Law.

Recommended hardening target: bind high-value authority artifacts to a canonical issuance service/process or hardware-backed/remote-attested custody boundary before claiming resistance to stolen-key possession.

## Passed attack classes
Ed25519 random forgery, wrong-key signatures, payload tampering, revoked-key signing, constitutional mutation, missing/disabled/duplicate directives, wrong-key governance signature, 1500 hostile Memory writes, quarantine, snapshot corruption, constitutional Memory overwrite, 25 COMA trip/recovery cycles, COMA execution bypass, Chromium Kernel pin provenance, authority-plane structural checks, dual-engine consensus fixture, executable invariant presence, and native Ed25519 altered-message verification.

## Pending
Signed Constitution end-to-end loader, live ChromiumOS verified-boot rootfs poisoning, Commander UI-language authority-creep runtime test, and full distributed Kernel-unavailable fallback test.

## Baseline
The same checkout completed the full npm verify chain with lint/build and all listed security checks passing. Production-readiness reported pass=true with two documented local-environment warnings for PostgreSQL TLS and plaintext Redis.

## Acquisition interpretation
Wave V does not justify an “invulnerable” claim. It provides 23 blocked attack conditions, exposes one real key-custody boundary limitation, and identifies four evidence gates requiring runtime infrastructure.

The acquisition stress manifest remains a manifest only. It explicitly requires each case to bind to a real executable test and forbids synthetic pass results.
