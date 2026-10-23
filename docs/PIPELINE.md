# Shiftcraft — pipeline specification

## Stage contracts

| Stage | Input | Output / postcondition | Failure and recovery |
| --- | --- | --- | --- |
| Load scenario | Floor, routes, orders, resources, constraints, seed | Validated initial shift state | Reject impossible references and unsupported rules with author diagnostics |
| Plan intervention | Player layout and dispatch choices | Versioned plan for the attempt | Validate collision, capacity, accessibility, and resource costs |
| Schedule shift | Initial state + plan + seed streams | Deterministic logical event queue | Rendering cannot change production event order |
| Process production | Station, movement, failure, quality events | Updated orders, queues, and resources | Conserve parts and record explicit scrap/rework |
| Present consequences | Logical state + selection | Animated floor, queues, warnings, and inspector | Pause and speed changes preserve simulation semantics |
| Debrief | Shift ledger + goals | Throughput, lead time, WIP, quality, and cause timeline | Incomplete shifts remain distinct from completed results |
| Retry and progress | Scenario + prior plan + supported unlocks | New attempt linked to baseline | Same seed comparison states any changed policy/config |

## Ordering and checkpoints

Use integer simulation ticks or an exact declared discrete-event time unit. Specify ties between completion, movement arrival, defect inspection, dispatch, and shift end. Each attempt records scenario, plan, engine, seed streams, and player command sequence. Checkpoints include pending events, all production state, progression state, and random-generator state. Save during a station operation cannot restart that operation at full duration unless the design explicitly records such behavior.

## Invariants across stages

- Every part occupies exactly one supported location/state at a logical instant.
- Station capacity, buffer capacity, and reserved travel destinations are enforced.
- Rework moves an existing part; it does not duplicate inventory.
- Completed output, WIP, scrap, and consumed inputs reconcile under the scenario’s bill of materials.
- Presentation speed and camera movement cannot affect logical production outcomes.

## Completion protocol

An operation starts by assigning a run identity and fingerprinting its effective configuration. Input validation completes before irreversible domain effects. Intermediate files remain staged and include an incomplete marker. Completed outputs are hashed and referenced by a manifest committed atomically with their accepted status. A crash before publication leaves recoverable intermediate work, not a plausible final report.

Retries identify the prior operation and preserve the original input references. A repair that changes semantics becomes a new revision with an explicit reason. Cancellation is honored at documented boundaries and records the last committed checkpoint. Importers reject incomplete outputs by default; diagnostic tools can inspect them only with an explicit incomplete status.

## Worked scenario

Illustrative shift: cutting completes a part, movement reserves a free inspection buffer slot, and inspection later detects a defect. The same part enters a rework route and consumes rework capacity before returning to inspection. The debrief attributes its lateness to recorded queue and processing intervals. Removing inspection can reduce visible waiting while allowing defects downstream; scenario goals define that tradeoff explicitly.

## Pipeline acceptance gate

The first vertical slice must demonstrate one ordinary case, one malformed input, one duplicate, and one interruption or recovery case. Its output includes input lineage and enough diagnostics to explain failure without reconstructing the operator's shell history. Domain-specific scenarios in [VALIDATION.md](VALIDATION.md) take precedence over generic throughput goals.
