# Shiftcraft — data model

## Canonical entities

| Entity | Identity / fields | Lifecycle / invariant |
| --- | --- | --- |
| ScenarioDefinition | Floor, stations, routes, goals, constraints, version | Validated before starting a shift |
| PlayerPlan | Layout, release and dispatch rules, allowed actions | Immutable starting plan plus recorded in-shift commands |
| Part / Order | Identity, route step, material state, due time | One supported location; rework preserves identity |
| Station / Buffer | Capacity, state, queues, processing parameters | Occupancy and reservations respect capacity |
| SimulationEvent | Time, sequence, cause, affected entities | Causal references support the debrief |
| ShiftAttempt | Scenario, plan, engine, seed, status, save refs | Retries link without overwriting outcomes |
| ProgressionState | Unlocked scenarios, upgrades, resources, version | Separate from one shift’s transient WIP |

## Domain semantics

Queue time, processing time, blocked time, starved time, and travel time are distinct intervals. Define whether metrics use wall time or logical shift time. Average WIP should be time weighted. Throughput counts accepted completed product under the scenario’s quality rule. Lead time uses release-to-completion semantics. Little’s Law can be an explanatory comparison only where its system boundary and observation assumptions are appropriate.

## Units, nulls, and identifiers

- Every part occupies exactly one supported location/state at a logical instant.
- Station capacity, buffer capacity, and reserved travel destinations are enforced.
- Rework moves an existing part; it does not duplicate inventory.
- Completed output, WIP, scrap, and consumed inputs reconcile under the scenario’s bill of materials.
- Presentation speed and camera movement cannot affect logical production outcomes.

An absent value, unknown value, invalid value, and numerical zero are distinct. Identifiers preserve source namespaces. Timestamps identify clock and precision. Collections specify whether their order is semantically significant. Statistical summaries specify population, filters, denominators, and time window. Serialization decisions must survive a cross-language round trip without precision loss.

## Storage and migration

Immutable source evidence is stored separately from derived views. A migration names source and destination versions, checks prerequisites, and produces a validation report. The prior accepted artifact remains available until the replacement passes its checks. Changes to meaning or units require a new schema major version. A path rename does not alter content identity; a corrected input changes lineage even when the filename is unchanged.

## Retention and portability

Keep manifests and compact diagnostics for accepted runs. Large raw inputs may live outside Git and carry availability and redistribution metadata. An export includes a relative artifact index and integrity digests, avoiding machine-specific absolute paths. Reports clearly identify missing or restricted inputs. User-generated or private information is included only in deliberately selected export scopes.
