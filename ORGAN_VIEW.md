# ORGANISM-INTERFACE — ORGAN VIEW

## Purpose

This is the common presentation model for an organ exposed through ORGANISM-INTERFACE.

It describes what an external user or another interface component can see about an organ. It does not prescribe how the organ is implemented internally.

## Organ card

Minimum visible information:

```text
ID
NAME
PURPOSE
STATUS
```

Extended information:

```text
INPUTS
OUTPUTS
CURRENT STATE
RELATIONS
DEPENDENCIES
RECENT EVENTS
MEMORY REFERENCES
EXPERIMENT REFERENCES
HISTORY
```

## Organ states

The interface should be able to distinguish at least:

```text
UNKNOWN
AVAILABLE
ACTIVE
IDLE
DEGRADED
PAUSED
FAILED
RECOVERING
RETIRED
```

An implementation may add more states when justified.

## Inputs and outputs

For every visible input/output, show where possible:

- identifier;
- human-readable meaning;
- data type or form;
- current availability;
- last known value or event;
- source/provenance;
- timestamp.

## Relations

An organ may be connected to:

- other organs;
- data sources;
- memory;
- experiments;
- graph objects;
- external interfaces.

The interface should allow navigation along these relations.

## Events

Recent organ activity should be presented as events rather than an undifferentiated text log.

Each event should expose, where available:

```text
EVENT ID
TIME
SOURCE
TYPE
INPUT
OUTPUT
STATUS
RESULT
```

## History

The organ view should provide a route from current state to relevant previous events and records.

The purpose is to make the path of change inspectable rather than showing only the latest snapshot.

## Experiment connection

An organ can be the subject, source, target or participant of an experiment.

The interface should link the organ view to the relevant experiment records.

## Machine representation

A machine-readable implementation should expose stable identifiers and explicit fields rather than requiring an AI to parse a visual layout.

Example conceptual object:

```text
organ {
  id,
  name,
  purpose,
  status,
  inputs[],
  outputs[],
  state,
  relations[],
  events[],
  history_refs[],
  experiment_refs[]
}
```

This is a conceptual interface shape, not yet a frozen wire schema.

## Internal implementation boundary

The organ view describes the visible contract only.

It does not define:

- the internal organ algorithm;
- the internal organ language;
- private implementation details;
- the Foundation.

Those are separate architectural layers.
