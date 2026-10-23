# Shiftcraft — implementation handoff

## Read order

Read PRODUCT, DATA_MODEL, PIPELINE, and VALIDATION before selecting a work package. This repository currently contains documentation and original identity artwork only. Do not infer an executable stack from proposed folder names.

## Proposed module hierarchy

| Planned path | Responsibility | Dependency boundary |
| --- | --- | --- |
| game/simulation/ | Scheduler, production state, routes, quality | No presentation dependencies |
| game/scenes/ | Floor, stations, HUD, debrief | Submit commands and render snapshots |
| game/application/ | Validated command and save boundary | Owns attempt lifecycle |
| game/scenarios/ | Versioned authored challenges | No executable arbitrary user scripts initially |
| game/assets/ | Original or attributed visual/audio assets | Rights recorded independently |
| adapters/ | Economy and experiment exports | Optional, versioned contracts |
| fixtures/ | Hand-solved production scenarios | Supports headless verification |

## First work packages

| Package | Deliverable | Acceptance / review |
| --- | --- | --- |
| WP-01 | Material state and timing specification | Paper walkthrough with conservation equation |
| WP-02 | Three-station headless scheduler | Blocking, starvation, and tie fixtures |
| WP-03 | Playable planning and running floor | Frame-speed independence and command validation |
| WP-04 | Rework and causal debrief | Trace one late order without invented causes |
| WP-05 | Save/retry and authored scenarios | Resume equivalence and player comprehension test |

## Engineering discipline

Each work package should fit one reviewable behavior. Define the fixture and expected output before broadening the interface. Keep domain code independent of the UI and external adapters. Add meaningful tests for state transitions, failure recovery, and numerical semantics; avoid tests that simply restate an implementation. When a contract changes, update its fixture and every affected importer together or preserve a compatibility layer.

Use a short-lived feature branch from main. A worktree is optional and should correspond to a bounded task; no permanent development branch is required. Commit the smallest coherent change with its documentation and validation evidence. Merge only after the package's acceptance criteria are met. Do not add empty frameworks, unverified installation commands, dummy benchmark results, or success badges.

## First reviewer checklist

The reviewer can explain where canonical state lives, what event order means, which values carry units, how a retry is recognized, and how a partial result is rejected. The reviewer can reproduce the smallest scenario without credentials or another project. A larger implementation plan should be revised from the observed first slice rather than treating every proposed directory as a requirement.
