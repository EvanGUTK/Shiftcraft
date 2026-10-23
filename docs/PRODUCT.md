# Shiftcraft — product specification

## Intended outcome

Create a compact 2D single-player operations game in Godot. Players inspect a small production floor, change layout and dispatch rules, run a shift, and review an explainable timeline. Seeded scenarios let players retry the same starting conditions and see the consequences of their decisions.

## Primary users and jobs

| User | Job | Successful outcome |
| --- | --- | --- |
| Strategy-game player | Solve a production bottleneck | Understand a failure, try an intervention, and observe its effects |
| Scenario designer | Teach one operational idea | Author a bounded challenge with explainable goals |
| Developer | Change game systems safely | Replay a minimized scenario and inspect state transitions |

## First journey

A shift begins with three workstations and a due-time target. Inspection becomes the bottleneck while upstream stations keep producing work in progress. The player pauses, changes release policy and buffer placement, then reruns the same scenario seed. The debrief shows station occupancy, queue time, rework, and each late order’s causal chain. A larger queue is no longer mistaken for more productive work.

## Functional requirements

| ID | Requirement | Acceptance evidence |
| --- | --- | --- |
| FR-01 | Separate simulation from frame rate | Different presentation speeds preserve logical outcome |
| FR-02 | Explain order delays | Debrief links waiting time to station, route, or resource state |
| FR-03 | Conserve material | Created, completed, WIP, scrapped, and consumed parts reconcile |
| FR-04 | Support reproducible retries | Same scenario, plan, engine, and seed repeat supported outcomes |
| FR-05 | Validate player plans | Invalid station placement cannot corrupt production state |
| FR-06 | Preserve save compatibility explicitly | Unsupported save version fails with a recoverable explanation |

## Scope and product constraints

Single-player 2D desktop slice with three workstation types, one product route, buffers, one movement model, one quality/rework mechanism, pause and speed controls, three authored scenarios, local saves, seeded retry, and an explanatory end-of-shift report.

No initial multiplayer, 3D factory construction, procedural campaign, real industrial training certification, direct employer datasets, large asset marketplace, player trading, or mobile release. EconomyLab integration follows a playable standalone loop.

## Product quality requirements

Every visible result identifies its source version and completeness. Repeating an action cannot silently create duplicate domain effects. Invalid input produces an actionable diagnostic tied to the field or event that failed validation. Long operations report progress and cancellation boundaries. A cancelled or interrupted operation is visibly different from a completed one.

The initial deployment is a single-user local workflow. Collaboration, tenancy, mobile apps, hosted services, billing, and distributed orchestration are separate scope decisions. An interface proposal must explain the user task it supports before adding new screens or infrastructure.

## Success and non-success

A headless reference scenario and its rendered version produce equivalent logical outcomes for the same plan and seed. Parts, time accounting, and resource transitions satisfy explicit invariants. Playtests establish whether users understand and enjoy the bottleneck puzzle; simulation correctness alone cannot establish fun.

Repository stars, document length, and interface polish do not substitute for the domain acceptance criteria. A result that cannot be explained or reproduced remains provisional. Scope expansion is deferred until the first complete scenario can be demonstrated and reviewed.

## Open product decisions

- Which three scenarios make the core loop enjoyable and understandable?
- What in-shift interventions should be allowed versus planning-only changes?
- Which travel abstraction is sufficient for the first floor size?
