# Deployment Readiness

## Current state

Ultra is a reproducible monorepo containing the Cranium OS operator surface and the hardened Core authority implementation. Both projects build independently from their lockfiles. CI checks each project separately so a UI change cannot silently bypass Core verification.

## Required production transition

The current browser adapter is deliberately marked as an unsigned local adapter. Before production deployment, implement an authenticated adapter to a running Core service with request signing or authenticated transport, server-side replay protection, verified receipt signatures, authorization at the service boundary, structured audit export, and operator-visible failure states.

Do not treat the local browser adapter as a production authority service. It exists for offline UI development and deterministic integration tests.

## Release gates

1. `npm ci` succeeds in both projects.
2. OS typecheck, tests, build, and production dependency audit pass.
3. Core typecheck, Jest tests, build, adversarial tests, and production dependency audit pass.
4. The CI workflow passes on the exact release commit.
5. Main branch protection requires review and the CI workflow.
6. Production secrets are supplied through a secret manager; none are committed.
7. The authenticated Core transport and receipt verification are tested in a staging environment.
8. The owner performs the final signing and deployment action.

## Environment prerequisites and explicit warnings

The current production-readiness check reports local PostgreSQL TLS disabled and local Redis plaintext. Those are development-compose conditions, not acceptable production defaults. Production deployment requires `CRANIUM_DB_SSL=true` with managed/private TLS for PostgreSQL and `rediss://` or equivalent private-network encryption for Redis. These are release prerequisites and must remain visible as gates, not footnotes to a passing local check.

The current Kernel security evidence was executed on Android/arm64 Termux. The Chromium Edition target is native x86-64. Runtime, verified-boot, and Kernel-outage evidence must therefore be executed on the target-class environment before a production Chromium Edition claim is made.

## Current architecture baseline

This document is part of the current Convertible Cranium documentation set. The canonical architecture is Dual-Substrate / Quad-Engine: Cranium AI, Synapse, Governance Review Juror One, and Governance Review Juror Two. The jurors have deliberately different review mandates and processes and neither issues authority.

Commander OS is the operational control surface. Cranium Listener is untrusted ingress. Miracle Memory provides governed continuity. Circuit Breaker / COMA provides cross-cutting runtime containment and recovery. The Convertible Cranium Kernel remains the sole canonical authority source.

The former Eight-Plane and Dual-Engine descriptions are historical framing only and must not be read as the current governance model.
