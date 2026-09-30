# Convertible Cranium Governed Transition Example
**Status:** Architecture example
**Date:** 2026-09-30

## Scenario
A user asks the Commander to perform a consequential operation, such as modifying a protected project resource.

The example is intentionally abstract. It documents the governance transition rather than granting any real-world capability.

## Step 1: Intent
The user expresses the desired outcome through Commander.
State: 'INTENT_RECEIVED'
The system records the request context required to evaluate it.

## Step 2: Cognition
Cranium AI interprets the request and proposes a concrete operation.
State: 'PROPOSED'
The proposal may include tool selection, parameters, dependencies, and expected result. None of that is authority.

## Step 3: Evidence assessment
Synapse evaluates the proposal against available evidence, identity, scope, trust context, and relevant constraints.
State: 'ASSESSED'
If evidence is insufficient, the system does not manufacture certainty. It can request clarification, gather permitted evidence, or stop.

## Step 4: Authority decision
The Kernel evaluates the assessed request against canonical authority rules, capability boundaries, receipts, replay state, lifecycle state, and constitutional constraints.

Possible states include:
- 'AUTHORIZED'
- 'DENIED'
- 'QUARANTINED'

The AI does not select among these states.

## Step 5: Execution
Only an authorized transition may cross into execution.
State: 'EXECUTING'
Commander or the governed runtime performs the action through the approved execution path.

## Step 6: Result
The runtime reports what actually happened.
State: 'COMPLETED' or an explicit failure state.
A model-generated claim that something happened is not sufficient evidence that it happened.

## Step 7: Receipt and continuity
The system records the authoritative decision and execution result. Miracle Memory may preserve authorized continuity and recovery-relevant state according to its governance rules.

## Step 8: Critical failure
If the runtime or cognitive evaluation reaches a critical containment condition, the Session Circuit Breaker can enter a tripped state. Execution is fenced, the system rolls back toward a defined checkpoint where supported, and recovery proceeds through the controlled state machine.

## The important distinction
A conventional agent loop can be summarized as:
'think -> call tool -> observe -> continue'

The Convertible Cranium governed loop is:
'intent -> propose -> assess -> authorize -> execute -> receipt -> continue'

That extra boundary is the architectural point. It is not decorative UI, and it is not a prompt instruction asking a model to behave itself.

## Evidence discipline
This example is a reference transition. It must not be presented as evidence that every future product integration already implements every transition shown here. Each deployed surface must be validated against its actual code, configuration, and runtime evidence.
