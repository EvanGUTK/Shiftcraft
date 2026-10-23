# Shiftcraft — operations and recovery plan

## Initial operating model

Ship a local desktop prototype using recorded export presets. Keep original art and sound attribution separate from generated runtime state. Use synthetic fictional factory scenarios; do not embed proprietary operational information. Automated scenario runs can later use headless Godot alongside manual playtest builds.

## Startup protocol

Load and validate the effective configuration; record its digest. Verify schema compatibility, output permissions, free storage, and required source availability. Recover or quarantine incomplete prior work before accepting new commands. A startup failure identifies the failed prerequisite and leaves accepted artifacts untouched. Show the exact active environment and mode in diagnostics.

## Failure handling

An impossible route, deadlock, blocked buffer, or exhausted resource produces a visible simulation condition with a causal trace. It must not silently teleport a part or discard work. Corrupt saves are quarantined while prior saves remain available. A missing art asset has a presentation fallback where feasible and never changes production accounting.

## Persistence and backup

Configuration, immutable manifests, and accepted outputs have distinct lifecycles. Before adopting a backup as valid, restore it into a separate location and verify artifact digests and a representative result. Checkpoint frequency is a measured tradeoff between storage and recoverable work. The application never assumes a process supervisor or the browser session is a durable state store.

## Diagnostics and resource boundaries

Logs record run, input, and correlation IDs. Counters distinguish attempts, accepted work, duplicates, failures, and retries. Disk exhaustion has a defined stop condition. Large files live outside Git. Credentials and user-private artifacts are excluded from logs and public diagnostics. External-service adapters record their endpoint class, permission needs, quotas, and recovery policy when implemented.

## Release lifecycle

Build from a recorded revision, validate setup in a clean environment, run the domain acceptance scenarios, and create release notes that identify known limitations. Schema migrations require a tested reverse or restore path. A rollback preserves raw evidence and records which derived outputs require recomputation. Public issue reports should use synthetic reproductions where possible.
