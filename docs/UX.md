# Shiftcraft — experience and visual direction

## Design thesis

Let the player see the production problem before opening a chart. Use spatial queues and simple overlays during play, then a focused causal debrief that invites one clear next experiment.

## Screen model

| Screen / surface | Primary task | Interaction and state |
| --- | --- | --- |
| Shift briefing | Understand the challenge | Goals, constraints, and one operational concept |
| Planning floor | Inspect and change the system | Readable station silhouettes, routes, capacity, and placement validation |
| Running shift | Observe consequences | Pause, speed, queue overlay, and selected-order inspector |
| Debrief | Understand outcome | Cause timeline, station occupancy, quality, and comparison |
| Scenario progression | Choose the next challenge | Unlocks tied to explicit scenario outcomes |

## Visual system

The repository identity uses warm industrial orange, slate floor geometry, restrained hazard yellow, strong workstation silhouettes, and uncluttered route overlays. The application should develop this direction with readable typography and deliberate information hierarchy. Numbers align by scale and unit. Visual emphasis belongs to the active question, selected event, unresolved discrepancy, or next action. Avoid filling the opening view with interchangeable statistic cards.

## Interaction rules

Selection persists when the user changes a filter, or the UI explains why the selected object is now outside the view. Comparisons preserve each run's identity and configuration. Loading, empty, incomplete, invalid, stale, and successful states are distinct. A result panel keeps the evidence drawer available so the user can inspect source events without losing context.

Keyboard navigation covers the primary journey. Color is reinforced by text, symbols, or line patterns. Tooltips expand unfamiliar terms but do not hide required units or failure reasons. Text and chart axes remain readable at normal laptop sizes. Destructive local edits provide a review of their exact scope and preserve recoverable prior revisions where feasible.

## First demonstration storyboard

Play a small bottleneck scenario with an intentionally poor release rule. Pause to inspect the queue, finish the shift, open a late order’s cause timeline, then retry the same starting conditions with a targeted intervention. Show the operational tradeoff rather than a guaranteed win.

The first demo uses synthetic or explicitly redistributable material and carries an illustrative label until the runtime produces it. The committed SVG banner is an identity asset, not evidence of a working application. Future screenshots should come from the application at a recorded revision.
