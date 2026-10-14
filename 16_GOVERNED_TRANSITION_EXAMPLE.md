# Convertible Cranium Governed Transition Example

**Status:** Architecture example, not proof that every integration implements this exact flow.

## Scenario

A user asks Commander to modify a protected project resource. The example traces the intended governance path without granting real-world capability.

## 1. Intent and ingress

The request enters through **Cranium Listener**, which treats input as untrusted. Commander provides the human-facing operational context but cannot authorize the operation.

State: `INTENT_RECEIVED`

## 2. Proposal and evidence binding

**Engine 1, Synapse** constructs a bounded proposal, derives relevant context, binds evidence references, performs its defined assessment, and commits the trace required by the contract.

State: `PROPOSED / ASSESSED`

Cranium AI may assist with interpretation and proposal generation, but its output is not authority. If context or evidence is insufficient, the system must not manufacture certainty.

## 3. Independent substrate assessments

**Engine 2A, Substrate A: Constitutional Authority** evaluates constitutional admissibility, policy constraints, scope, prohibited actions, and approval requirements.

Question: **“May we?”**

**Engine 2B, Substrate B: Evidence Grounding** evaluates evidence provenance, integrity, contradiction, freshness/relevance, and sufficiency.

Question: **“Is it so?”**

These are distinct review paths. Neither substrate issues canonical authority. Their findings are evidence inputs to the Kernel, not votes.

## 4. Kernel convergence and authority decision

**Engine 3, Convertible Cranium Kernel** validates the proposal, A/B findings, applicable version bindings, capability and authorization context, replay state, current state, evidence lineage, and required convergence conditions.

Possible outcomes include an authorized transition, explicit denial/rejection, or quarantine according to the applicable contract. The Kernel alone issues canonical authority.

State: `AUTHORIZED`, `DENIED`, or `QUARANTINED`

No model or substrate selects the canonical outcome. Failure to meet the required conditions must fail closed.

## 5. Governed execution

Only a valid Kernel-authorized transition may enter the approved execution path.

State: `EXECUTING`

Commander or the governed runtime performs the operation within the granted scope. A local UI state or proposed tool call is not proof that execution occurred.

## 6. Result, receipt, and continuity

The runtime reports the observed outcome. The system records the governed transition and relevant receipt/proof/lineage. Miracle Memory may preserve continuity and recovery-relevant state under its governance rules.

State: `COMPLETED` or an explicit failure/recovery state.

A model-generated claim that something happened is not sufficient evidence that it happened.

## 7. Critical failure and containment

Circuit Breaker / COMA may fence execution, freeze or quarantine state, preserve evidence, and permit controlled recovery where supported by the implementation contract. It remains a cross-cutting safety mechanism, not a second authority source.

## The important distinction

A conventional agent loop can be summarized as:

`think → call tool → observe → continue`

The intended Convertible Cranium governed path is:

`intent → Synapse proposal/evidence → Substrate A + Substrate B → Kernel decision → governed execution → receipt/proof/lineage`

The extra authority boundary is architectural. It is not decorative UI or a prompt instruction asking a model to behave itself.

## Evidence discipline

This is a reference transition. It must not be presented as proof that every future product integration already implements every state shown here. Each deployed surface must be checked against its actual code, configuration, tests, and runtime evidence.
