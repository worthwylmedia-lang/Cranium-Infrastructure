# Synapse

Synapse is the bounded evidence and assessment plane. It evaluates evidence, trust conditions, attestations, scope, integrity, and related constraints.

Synapse does not authorize. Foreign issuers, tampered evidence, replay, and invalid scope must fail closed where those paths are implemented.

## Current architecture position

This subsystem participates in the current Dual-Substrate / Quad-Engine architecture. It does not create canonical authority independently. The Convertible Cranium Kernel remains the sole canonical authority source; Governance Review Juror One and Governance Review Juror Two are distinct review paths, not authority issuers.
