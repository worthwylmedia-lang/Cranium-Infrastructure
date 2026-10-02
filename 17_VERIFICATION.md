# Verification

Verification is evidence, not marketing language.

## Standardized revision

Current evidence is standardized on clean Kernel commit `0d0ae41f78e3f23da073390285d401c4a215dc6a`. The prior `e36bdba2fe0a448473f94250920e751c95e1d3e0` clean-clone checkpoint remains historical and is not mixed into the current Wave V result. The earlier Wave V implementation revisions `60e0089`, `0daa563`, and `83bc556` are preserved as chronology, not as competing current baselines.

Local executable verification at the standardized revision completed with Node v24.18.0 on Android/arm64 Termux. The Wave V suite reports **26 PASS conditions, 0 vulnerability findings, and 3 evidence gates pending**. The 26 executed conditions are classified as **17 hostile attacks** and **9 controls/checks**. Pending gates are V5-B live ChromiumOS verified-boot poisoning, V6-B Commander UI-language authority creep under runtime interaction, and V8-B end-to-end Kernel-unavailable behavior.

The target platform is native x86-64 ChromiumOS. Android/arm64 Termux is a development/verification environment and must not be described as the target runtime.

## Constitution proof count

The constitution check defines **8 Prime Directives and 8 executable engine-proof markers**. Earlier output said `engine_proofs=7` despite checking eight markers; that reporting defect has been corrected in the standardized revision. The eighth proof is `assertConstitutionalTransition`.

## Reproducibility

The canonical attack/test ledger is `evidence/TEST_AND_ATTACK_LEDGER_2026-09-30.md`. Each row identifies the condition type, exact status, and evidence boundary. A reviewer should rerun `npm ci`, `npm run verify`, and `npm run verify:denial-semantics` against the standardized revision and compare the observed runtime and outputs.

## Hosted reproduction status

A GitHub-hosted x64 run is desirable for independent environment reproduction, but the local Kernel remote currently points to `https://github.com/worthwyl2022-cloud/cranium-kernel.git`, and that repository is not present in the connected GitHub account. Therefore no hosted x64 result is claimed here. This is an access/repository-publication gate, not a fabricated pass.

## Scope limits

This evidence is self-run. It is not third-party certification, HSM/KMS certification, ChromiumOS runtime certification, verified-boot certification, or a guarantee about future revisions or deployments.

## Current architecture baseline

This document is part of the current Convertible Cranium documentation set. The canonical architecture is Dual-Substrate / Quad-Engine: Cranium AI, Synapse, Governance Review Juror One, and Governance Review Juror Two. The jurors have deliberately different review mandates and processes and neither issues authority.

Commander OS is the operational control surface. Cranium Listener is untrusted ingress. Miracle Memory provides governed continuity. Circuit Breaker / COMA provides cross-cutting runtime containment and recovery. The Convertible Cranium Kernel remains the sole canonical authority source.

The former Eight-Plane and Dual-Engine descriptions are historical framing only and must not be read as the current governance model.
