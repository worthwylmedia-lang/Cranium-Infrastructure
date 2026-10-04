# Circuit Breaker / COMA

Runtime containment and deterministic recovery.

Critical conditions can trip an execution fence, roll back to a valid checkpoint, and permit controlled recovery. Runtime state cannot manufacture authority.

## Current architecture position

This subsystem participates in the current Dual-Substrate / Quad-Engine architecture. It does not create canonical authority independently. The Convertible Cranium Kernel remains the sole canonical authority source; Governance Review Juror One and Governance Review Juror Two are distinct review paths, not authority issuers.
