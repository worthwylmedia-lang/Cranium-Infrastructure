# Reproducibility Checkpoint

## Kernel checkpoint

- Repository: Convertible Cranium Kernel
- Branch at checkpoint: origin/main
- Commit: 0d0ae41f78e3f23da073390285d401c4a215dc6a
- Verification date: 2026-09-30
- Runtime: Node v24.18.0
- npm: 11.19.1
- package-lock.json SHA-256: cf38054cc1326a816c80fdb92b63209242b9cde2dd9cae94002b9aa40373f199
- Host: Android/arm64 Termux
- Clone condition: clean clone
- Commands:
  - npm ci
  - npm run verify
  - npm run verify:denial-semantics
- Recorded exit code: 0

## What this proves

The checkpoint records that the project's documented verification commands completed successfully on the stated checkout and runtime.

It does **not** by itself prove:
- independent review,
- absence of undiscovered defects,
- HSM or hardware-backed key custody,
- production deployment security,
- ChromiumOS boot/runtime correctness,
- legal ownership or patentability.

## Reviewer reproduction

A reviewer needs access to the exact Kernel commit and its lockfile, a supported Node v24 runtime, and a clean clone. The reviewer should record:

1. repository URL and resolved commit;
2. Node and package-manager versions;
3. lockfile hash;
4. exact commands;
5. complete stdout/stderr;
6. exit code;
7. any environment-specific warnings;
8. resulting artifact hashes where applicable.

The current acquisition binder records the project-side checkpoint. Independent reproduction should be recorded as a separate evidence record and should not overwrite the self-attested record.

## Access boundary

The acquisition binder is the public review surface. Historical engineering repositories may have different visibility or authenticated ownership. If a reviewer cannot clone the pinned Kernel revision, the verification status remains self-attested and the access limitation must be reported explicitly.

## Current architecture baseline

This document is part of the current Convertible Cranium documentation set. The canonical architecture is Dual-Substrate / Quad-Engine: Cranium AI, Synapse, Governance Review Juror One, and Governance Review Juror Two. The jurors have deliberately different review mandates and processes and neither issues authority.

Commander OS is the operational control surface. Cranium Listener is untrusted ingress. Miracle Memory provides governed continuity. Circuit Breaker / COMA provides cross-cutting runtime containment and recovery. The Convertible Cranium Kernel remains the sole canonical authority source.

The former Eight-Plane and Dual-Engine descriptions are historical framing only and must not be read as the current governance model.
