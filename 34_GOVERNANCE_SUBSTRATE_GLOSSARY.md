# Governance Substrate Glossary

Definitions for reviewers, engineers, OS architects, and acquisition diligence teams.

## Authority-Bound

A system property in which authority cannot emerge from cognition, evidence, memory, UI, runtime, consensus, or other non-authoritative signals.

## Canonical Authority

Authority issued only by the Kernel under governed transition rules.

## Governed Transition

The sequence:

intent → proposal → evidence → governed request → Kernel decision → execution → receipt → continuity

Expand via 12_AUTHORITY_FLOW.md.

## Dual-Substrate / Quad-Engine

The current architecture consists of four distinct engines across two governance substrates: Cranium AI for intelligence/orchestration, Synapse for evidence/assessment, Governance Review Juror One for constructive review, and Governance Review Juror Two for adversarial review. The jurors deliberately use different mandates and processes. Neither juror issues authority. The Kernel remains the sole canonical authority source.

## Miracle Memory

Governed continuity supporting identity, contradiction tracking, quarantine, and recovery context.

## COMA / Session Circuit Breaker

Containment and recovery mechanisms supporting rollback, checkpoint integrity, and controlled half-open recovery.

## Constitution

Durable constraints, proofs, and invariants governing transitions.

## Receipts & Attestation

Evidence associated with governed transitions, including integrity and replay-resistant provenance mechanisms where implemented.

## Chromium Edition

The ChromiumOS integration layer for the Convertible Cranium product surface. Boot, runtime, and verified-boot evidence remain a defined pending gate.

## Provenance

Historical lineage connecting the acquisition-facing surface to the legacy engineering ecosystem and its verified source revisions.

## Migration Path

clean surface → secret sweep → structural gate → curated construction → Kernel reconciliation → Chromium evidence gate → authenticated migration → provenance preservation

## Evidence States

PASS indicates evidence was verified for the stated scope. PENDING indicates an open implementation or evidence gate. NOT CLAIMED indicates that no unsupported assertion is being made.

## Authority Invariant

No combination of cognitive output, evidence, memory, UI state, runtime state, agent consensus, external attestation, or other non-authoritative signal may synthesize, infer, inherit, or substitute for canonical authority. Canonical authority exists only when the Convertible Cranium Kernel issues a valid governed authority transition under applicable law, capability, scope, evidence, lifecycle, and integrity requirements.

## Reviewer Rule

Definitions in this glossary describe architectural roles and evidence posture. They do not themselves establish implementation proof. Evidence must be traced to the relevant source, revision, test, artifact, or independent review record.

## Current architecture baseline

This document is part of the current Convertible Cranium documentation set. The canonical architecture is Dual-Substrate / Quad-Engine: Cranium AI, Synapse, Governance Review Juror One, and Governance Review Juror Two. The jurors have deliberately different review mandates and processes and neither issues authority.

Commander OS is the operational control surface. Cranium Listener is untrusted ingress. Miracle Memory provides governed continuity. Circuit Breaker / COMA provides cross-cutting runtime containment and recovery. The Convertible Cranium Kernel remains the sole canonical authority source.

The former Eight-Plane and Dual-Engine descriptions are historical framing only and must not be read as the current governance model.
