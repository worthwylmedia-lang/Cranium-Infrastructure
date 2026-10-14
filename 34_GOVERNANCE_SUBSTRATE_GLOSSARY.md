# Governance Substrate Glossary

Definitions for reviewers, engineers, OS architects, and acquisition diligence teams.

## Authority-bound

A system property in which canonical authority cannot emerge from cognition, evidence, memory, UI, runtime, consensus, or other non-authoritative signals.

## Canonical authority

Authority issued only by the Convertible Cranium Kernel under governed transition rules.

## Governed transition

The intended sequence:

`untrusted ingress → Synapse proposal/evidence binding → Substrate A + Substrate B assessment → Kernel convergence/decision → governed execution → receipt/proof/lineage`

See [Authority Flow](12_AUTHORITY_FLOW.md).

## Dual-Substrate / Quad-Engine

The current architecture consists of four engines:

1. **Engine 1, Synapse:** proposal/context processing, evidence binding, assessment, and trace.
2. **Engine 2A, Substrate A:** Constitutional Authority, “May we?”
3. **Engine 2B, Substrate B:** Evidence Grounding, “Is it so?”
4. **Engine 3, Kernel:** canonical convergence and authority transition.

Cranium AI is a cognition/application surface, not an authority-path engine. Substrates A and B have distinct responsibilities; neither grants authority. Convergence is not voting.

## Substrate A: Constitutional Authority

The governance path for constitutional admissibility, policy constraints, scope, prohibited actions, and approval requirements.

## Substrate B: Evidence Grounding

The governance path for evidence provenance, integrity, contradiction, freshness/relevance, and sufficiency.

## Miracle Memory

Governed continuity supporting identity, provenance, contradiction tracking, quarantine, snapshots, and recovery context.

## Metabolic Memory v2

Resource-governance behavior over memory atoms. It does not grant authority; locked/identity atoms receive the protection specified by its documented rules.

## COMA / Circuit Breaker

Cross-cutting containment and recovery mechanisms supporting freeze/quarantine, evidence preservation, and controlled resume under the applicable implementation contract.

## Constitution

Versioned constraints, policies, and invariants relevant to governed transitions. A constitutional finding is not itself canonical authority.

## Receipts and attestation

Evidence associated with governed transitions, including integrity and replay-resistant provenance mechanisms where implemented. Receipts and attestations do not issue authority.

## Chromium Edition

The ChromiumOS integration layer for the Convertible Cranium product surface. Native x86-64 image build, boot, runtime, and verified-boot evidence remain pending until captured and reviewed.

## Provenance

Technical history connecting artifacts to repositories, revisions, commits, contributors, and recorded development history. Technical provenance is relevant to, but does not by itself establish, legal ownership.

## Evidence states

- **Verified:** supported by a named artifact, executable check, or reproducible repository state for the stated scope.
- **Self-attested:** recorded from project execution without independent third-party verification.
- **Pending:** an identified implementation, environment, or evidence gate remains open.
- **Not claimed:** no unsupported assertion is made.

## Authority invariant

No combination of cognitive output, evidence, memory, UI state, runtime state, agent consensus, external attestation, or other non-authoritative signal may synthesize, infer, inherit, or substitute for canonical authority. Canonical authority exists only when the Convertible Cranium Kernel issues a valid governed authority transition under applicable capability, scope, evidence, lifecycle, and integrity requirements.

## Reviewer rule

Definitions describe architectural roles and evidence posture. They do not themselves establish implementation proof. Evidence must be traced to the relevant source, exact revision, test, artifact, or independent review record.
