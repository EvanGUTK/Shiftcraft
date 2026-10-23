# Shiftcraft — game design and scenario bible

## Player fantasy

You inherit a small chaotic production floor and make it work better. The pleasure comes from noticing a cause, trying a sensible change, and watching the flow respond. The game should reward diagnosis, quality, and measured experimentation rather than requiring rapid clicking.

## First three scenarios

**The growing queue:** Three stations have mismatched capacity. The player learns that feeding the line faster can increase WIP without improving completed output. Provide a clear queue overlay and one relevant release-policy intervention.

**The shortcut:** Moving inspection or reducing its frequency appears to improve speed but changes downstream defect consequences under explicitly authored rules. The debrief shows rework and quality effects so the tradeoff is understandable rather than arbitrary punishment.

**The missing tool:** A shared tool or limited resource blocks multiple workstations. The player inspects reservations and routes, then adjusts placement, availability, or dispatch. Start with one resource type and avoid a large inventory-management layer.

## Goals and scoring

Each challenge declares completion, due-time, quality, and resource constraints. Present the metric definitions before the shift. Avoid one opaque score that hides tradeoffs. A scenario may award distinct achievements for meeting demand, preserving quality, or reducing unnecessary WIP. Their meaning must be visible and testable.

## Difficulty and accessibility

Pause and speed controls are central. Early scenarios introduce one concept and offer a readable cause explanation. Tooltips explain units and state, while the floor remains legible without permanent overlays. Color is never the only indicator of a defect, blocked station, or selected route.

## Expansion conditions

Additional product routes, worker specialization, stochastic breakdowns, campaign progression, and economy integration follow evidence that the first three scenarios are enjoyable. Multiplayer and large procedural factories require separate architectural and product decisions; they are not implicit obligations of the first release.
