# Shiftcraft — milestone roadmap

Milestones are ordered by dependencies, not promised calendar dates. No implementation milestone is complete in this blueprint revision.

| Milestone | Deliverable | Exit criteria |
| --- | --- | --- |
| M0 — Design contract | Core loop, material states, authored scenario | Paper walkthrough and metric definitions reviewed |
| M1 — Headless slice | Three-station logical production | Hand-solved material and timing fixtures pass |
| M2 — Playable floor | Planning, movement, pause, and inspection | Rendered and headless logical outputs agree |
| M3 — Quality and debrief | Rework, goals, and causal reports | Lateness trace and material conservation demonstrated |
| M4 — Save and scenarios | Local persistence and three challenges | Resume equivalence and invalid-save handling |
| M5 — Playtest and integration | Measured usability and optional economy mapping | Players can explain a bottleneck; adapter scope verified |

## Definition of done

A milestone has a bounded scope, implementation revision, synthetic reproduction input, expected output, validation evidence, and a short demonstration. Setup instructions work in a clean supported environment. Failure behavior is documented alongside the ordinary case. The project status file advances only when the exit criteria are met.

## Scope control

The first milestone cannot depend on a sibling project or hosted service. Optional integrations follow standalone correctness. Performance optimization follows a representative workload and a repeatable baseline. New UI surfaces require a demonstrated user task. Dependencies and licenses are recorded when adopted; exact versions are pinned with implementation.

## Work sequencing

Review [IMPLEMENTATION_HANDOFF.md](IMPLEMENTATION_HANDOFF.md) before creating worktrees. Keep contract changes separate from adapter changes where that allows a reviewer to understand compatibility. A change that invalidates an earlier milestone must update its acceptance evidence and status, not simply append a new roadmap item.

## Deferred expansion

No initial multiplayer, 3D factory construction, procedural campaign, real industrial training certification, direct employer datasets, large asset marketplace, player trading, or mobile release. EconomyLab integration follows a playable standalone loop.

Open decisions in [DECISIONS.md](DECISIONS.md) should be resolved by a small experiment or a documented requirement. They are not a reason to build every alternative.
