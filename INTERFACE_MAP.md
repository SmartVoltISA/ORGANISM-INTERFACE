# ORGANISM-INTERFACE — INTERFACE MAP

## 1. Purpose

This document describes the visible and operational areas of the organism interface.

It is an interface map, not a definition of the organism's Foundation and not the specification of the internal organ language.

## 2. Top-level map

```text
ORGANISM-INTERFACE
│
├── HOME
│   ├── overview
│   ├── current state
│   └── recent activity
│
├── OBSERVATION
│   ├── state
│   ├── organs
│   ├── graph
│   ├── memory
│   └── history
│
├── ARCHITECTURE
│   ├── structure
│   ├── layers
│   ├── organs
│   ├── relations
│   └── dependencies
│
├── GRAPH
│   ├── nodes
│   ├── edges
│   ├── paths
│   └── changes
│
├── MEMORY
│   ├── records
│   ├── events
│   ├── results
│   └── provenance
│
├── EXPERIMENTS
│   ├── questions
│   ├── plans
│   ├── runs
│   ├── observations
│   ├── results
│   └── replication
│
├── ORGANS
│   ├── registry
│   ├── organ view
│   ├── inputs
│   ├── outputs
│   ├── state
│   └── relations
│
├── RECOVERY
│   ├── points
│   ├── versions
│   ├── restore status
│   └── recovery history
│
└── WORKSPACE
    ├── human
    ├── AI
    ├── engineering
    └── external contributions
```

## 3. Main navigation

Every interface implementation should make the following areas discoverable without requiring knowledge of internal implementation details:

- Home;
- Observation;
- Architecture;
- Graph;
- Memory;
- Experiments;
- Organs;
- Recovery;
- Workspace.

## 4. Organ view

An organ should be presented through a common view containing, where available:

```text
IDENTITY
PURPOSE
STATUS
INPUTS
OUTPUTS
CURRENT STATE
RELATIONS
DEPENDENCIES
RECENT EVENTS
EXPERIMENTS
HISTORY
```

The common view is an interface convention. It does not imply that all organs have identical internal implementations.

## 5. State view

The state view answers:

- what is known now;
- what was observed;
- when it was observed;
- where it came from;
- what changed;
- what remains unresolved.

The interface should preserve the difference between observation, interpretation and verified result.

## 6. Graph view

The graph view should allow a user or machine to move from:

```text
node → relation → node → relation → node
```

and inspect the meaning and available history of each connection.

## 7. Memory and history view

Memory and history should be navigable by:

- time;
- object;
- organ;
- experiment;
- event;
- result;
- relation.

The interface should make it possible to follow a result back toward its source when provenance is available.

## 8. Experiment view

A standard experiment view contains:

```text
QUESTION
CONTEXT
HYPOTHESIS
METHOD
INPUTS
RUNS
OBSERVATIONS
RESULT
INTERPRETATION
LIMITATIONS
STATUS
NEXT STEP
```

The interface must distinguish a planned experiment from an executed experiment.

## 9. Recovery view

Recovery is exposed as an operational area with:

- available recovery points;
- source version;
- target state;
- verification status;
- recovery result;
- history.

The interface should never represent an unverified recovery as verified.

## 10. Human view

The human view prioritizes:

- clarity;
- current state;
- navigation;
- explanations;
- history;
- experiments;
- practical actions.

## 11. AI / machine view

The machine view prioritizes:

- stable identifiers;
- explicit states;
- structured records;
- provenance;
- predictable navigation;
- machine-readable results;
- explicit errors;
- explicit unavailable data.

An AI should not have to infer the interface structure from prose alone.

## 12. Engineering view

The engineering view exposes deeper structure:

```text
architecture
    ↓
organs
    ↓
interfaces
    ↓
state
    ↓
graph
    ↓
memory/history
    ↓
experiments
    ↓
recovery
```

It is intended for building, diagnosing and extending interface implementations.

## 13. External contribution view

External human or AI work is presented separately from canonical organism information.

The interface may link to external research, journals, replications, critiques and proposals, while keeping their origin and status visible.

## 14. Non-goals

This map does not define:

- the Foundation;
- canonical organism invariants;
- internal organ language;
- authorization policy;
- implementation-specific security mechanisms.

Those belong to their respective architectural layers.

## 15. Current status

This is the first interface map. Items describe the intended interface surface and may be implemented progressively.
