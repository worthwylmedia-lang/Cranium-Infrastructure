# Kernel Verification Record — 2026-09-30

Verified SHA: `0d0ae41f78e3f23da073390285d401c4a215dc6a`
Repository: `cranium-kernel`
Runtime: Node v24.18.0
Host: Android/arm64 Termux
State: clean working tree at the verified revision

## Commands

```text
npm ci
npm run verify
npm run verify:denial-semantics
```

The standardized revision was created after the Wave V classification/proof-count corrections and was re-executed through the Kernel verification chain. Wave V reports 26 PASS conditions, 0 vulnerability findings, and 3 pending evidence gates, classified as 17 hostile attacks and 9 controls/checks.

The local execution environment is Android/arm64 Termux. The Chromium Edition target is native x86-64. This record is therefore development/verification evidence, not target-runtime certification.

## Hosted reproduction gate

The local Git remote points to `https://github.com/worthwyl2022-cloud/cranium-kernel.git`, but the repository is not present in the connected GitHub account. No hosted x64 reproduction is claimed until the canonical Kernel repository is published or the remote is corrected.

## Scope

This record is self-run evidence. It is not third-party audit, HSM/KMS certification, hardware-backed key certification, ChromiumOS runtime certification, verified-boot certification, or a guarantee about future revisions.
