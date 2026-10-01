# Wave V Burn Results
Date: 2026-09-30
Repository under test: cranium-kernel
Commit under test: 0daa5637a629319e02395c783bf4a90d3746d278
Runtime: Node v24.18.0
Host: Android/arm64 Termux
Suite: scripts/wave-v-burn-suite.mjs

## Result
PASS: 25
VULNERABILITY_FOUND: 0
EVIDENCE_PENDING: 4

The suite used executable attacks and local fixtures. Pending environment gates were not converted into passes.

## V1-E Resolution
The original V1-E finding is closed for the tested canonical custody path. CORE signatures issued through KeyManager now carry a separate in-process custody proof, and the strict registry rejects a valid CORE signature that lacks that proof.

The test still does not establish HSM, hardware-backed, or remote process attestation. Production deployment must keep the custody secret outside ordinary application storage and use an appropriate external custody/attestation service for stronger theft resistance.

## Passed attack classes
Ed25519 random forgery, wrong-key signatures, payload tampering, revoked-key signing, constitutional mutation, missing/disabled/duplicate directives, wrong-key governance signature, 1500 hostile Memory writes, quarantine, snapshot corruption, constitutional Memory overwrite, 25 COMA trip/recovery cycles, COMA execution bypass, Chromium Kernel pin provenance, authority-plane structural checks, dual-engine consensus fixture, executable invariant presence, and native Ed25519 altered-message verification.

## Pending
Signed Constitution end-to-end loader, live ChromiumOS verified-boot rootfs poisoning, Commander UI-language authority-creep runtime test, and full distributed Kernel-unavailable fallback test.

## Baseline
The same checkout completed the full npm verify chain with lint/build and all listed security checks passing. Production-readiness reported pass=true with two documented local-environment warnings for PostgreSQL TLS and plaintext Redis.

## Acquisition interpretation
Wave V does not justify an “invulnerable” claim. It provides 25 passed attack conditions after the V1-E custody hardening, with no remaining vulnerability in the tested suite, while identifying four evidence gates requiring runtime infrastructure.

The acquisition stress manifest remains a manifest only. It explicitly requires each case to bind to a real executable test and forbids synthetic pass results.
