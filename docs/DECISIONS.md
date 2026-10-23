# Shiftcraft — architecture decision register

Status meanings: **proposed** is the current blueprint choice; **open** needs a bounded experiment before implementation. No choice here proves runtime behavior.

| ID | Status | Decision | Alternative / consequence |
| --- | --- | --- | --- |
| ADR-001 | Proposed | 2D single-player first | Keeps operational readability and content scope manageable |
| ADR-002 | Proposed | Logical state separate from Godot scenes | More explicit boundaries; supports headless verification |
| ADR-003 | Proposed | Authored scenarios before procedural generation | Allows deliberate teaching and interpretable goals |
| ADR-004 | Proposed | Simplified movement first | Physical realism expands only where it changes meaningful decisions |

## Open questions and resolution method

- **Which three scenarios make the core loop enjoyable and understandable?** Resolve with a minimal fixture, an explicit requirement, or a recorded compatibility check before expanding the corresponding milestone.
- **What in-shift interventions should be allowed versus planning-only changes?** Resolve with a minimal fixture, an explicit requirement, or a recorded compatibility check before expanding the corresponding milestone.
- **Which travel abstraction is sufficient for the first floor size?** Resolve with a minimal fixture, an explicit requirement, or a recorded compatibility check before expanding the corresponding milestone.

## Change protocol

Each new decision records context, considered alternatives, selected option, downside, acceptance evidence, and the condition that would trigger reconsideration. Superseded decisions remain in the register. A rejected alternative is recorded only when it explains a continuing tradeoff. Review decisions at milestone boundaries rather than changing foundational contracts incidentally during UI work.
