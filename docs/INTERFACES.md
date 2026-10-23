# Shiftcraft — interfaces and integration specification

All interfaces below are proposed contracts. Names describe responsibilities rather than installed APIs.

| Boundary | Request / input | Response / output | Guarantee |
| --- | --- | --- | --- |
| LoadScenario | Versioned scenario | Validated logical state or author diagnostics | No unresolved floor or route references |
| SubmitCommand | Attempt + logical command time + action | Accepted action event or reason | Commands pass constraints before state mutation |
| AdvanceSimulation | Target logical event/time boundary | State snapshot and emitted events | Rendering-independent ordering |
| SaveAttempt | Accepted checkpoint boundary | Versioned state and pending events | Resume preserves supported behavior |
| ExportDebrief | Completed or explicit partial attempt | Metrics, causal timeline, comparison refs | Units and incomplete state visible |
| EconomyMapping | Supported rewards/purchases/unlocks | EconomyLab-compatible subset | Factory physics and scheduling stay local |

## Domain-specific behavior

Scenes communicate through a narrow application boundary rather than manipulating arbitrary station nodes. Scenario formats separate authored intent from engine runtime objects. A future mod format must define supported commands and validation separately. EconomyLab can evaluate reward pacing, while Shiftcraft remains authoritative for production success and material movement.

## Import and export rules

Imports validate schema version, domain units, source identity, completeness, payload hash, and declared capabilities. An unsupported optional capability is surfaced to the caller; mandatory capability gaps reject the request. Exporters include contract version and a provenance manifest, and must not require direct access to an internal database.

Request identities are stable across retries. Repeated completed requests return the recorded result or an explicit duplicate result; requests with an existing identity and different content are rejected. Timeouts distinguish a known rejection from an unknown external outcome. Consumers cannot infer that an action did not happen merely because a response was lost.

## Shared conventions

Use [CONTRACTS.md](CONTRACTS.md) for envelope, time, precision, and compatibility conventions. File-based interoperability is the first integration target. Binary or local process protocols can follow after a measured need and a conformance test. A contract's ownership is recorded in [ECOSYSTEM.md](ECOSYSTEM.md).

## Consumer conformance checklist

The future adapter must demonstrate valid import, unsupported-version rejection, precision-preserving round trip, duplicate handling, corrupt-artifact rejection, and recovery from a truncated output. This checklist specifies future evidence; it does not assert that an adapter already exists.
