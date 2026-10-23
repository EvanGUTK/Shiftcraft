# Shiftcraft — validation and benchmark plan

This is a proposed validation plan. No runtime results or benchmark numbers are claimed.

## Domain scenario matrix

| Scenario | Expected behavior | Evidence |
| --- | --- | --- |
| Frame-rate variation | Logical outcomes remain equivalent | State and event digest comparison |
| Full downstream buffer | Upstream blocking is visible | Capacity and waiting trace |
| Rework loop | No part duplication | Material conservation report |
| Same-time completion | Stable dispatch tie policy | Golden event trace |
| Save during processing | Resume preserves remaining work | Checkpoint versus uninterrupted attempt |
| Invalid floor plan | Rejected before shift mutation | Placement diagnostic |
| Unreachable goal | Clear failed/partial debrief | Goal reason and causal evidence |

## Measurement protocol

Measure simulation events per logical shift, CPU and memory, rendering frame times, save/restore time, and debrief latency on recorded hardware. Playtest task completion, explanation accuracy, and subjective engagement separately. Use profiler captures to justify moving any hot GDScript path into C++; do not optimize hypothetical large factories before the first slice is playable.

## Reproducibility record

Record source revision, environment and dependency lock, operating system, CPU/GPU where relevant, workload identity, input size, data distribution, random seeds, concurrency, warm-up policy, repetitions, and output digests. Report variability and failures as well as the preferred statistic. Distinguish pure kernel timing from parsing, serialization, storage, network, and UI costs. Comparisons use the same semantics and workload.

## Correctness before speed

A headless reference scenario and its rendered version produce equivalent logical outcomes for the same plan and seed. Parts, time accounting, and resource transitions satisfy explicit invariants. Playtests establish whether users understand and enjoy the bottleneck puzzle; simulation correctness alone cannot establish fun.

Use a small independent reference or analytically solved fixture where feasible. A second implementation that copies the same assumptions is not independent evidence of realism. Numerical comparisons define tolerances; discrete identifiers, units, and state transitions require exact agreement. Every discovered defect becomes a minimized regression scenario with its original cause explained.

## Publication rules

Illustrative values must be labeled. A benchmark badge is added only when its method and source artifacts are available. Missing data, incomplete runs, rejected inputs, and failed experiments remain in the evaluation record. No annualized financial performance, behavioral realism, or platform fidelity is inferred from a short convenient sample.
