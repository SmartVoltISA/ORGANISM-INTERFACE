# ORGANISM-INTERFACE — VIEWS

## Why multiple views

The organism is one system, but different users need different ways to see it.

The interface therefore has two primary user levels and one engineering view.

## 1. Guest / External

Purpose: understand and explore the published organism.

Typical areas:

- overview;
- architecture overview;
- visible organs;
- graph overview;
- published memory/history;
- experiments and results;
- documentation;
- external research.

The guest view should explain what the user is seeing instead of assuming specialist knowledge.

## 2. Internal / Operator

Purpose: work with the available organism functions.

Typical areas:

- live observation;
- organ selection;
- state inspection;
- graph navigation;
- memory/history;
- experiments;
- diagnostics;
- approved operations;
- recovery;
- work history.

The operator view is a working console, not merely a documentation page.

## 3. Engineering / Architect

Purpose: understand and construct the system itself.

Typical areas:

- architecture;
- organ registry;
- interfaces;
- dependencies;
- graph topology;
- state model;
- memory model;
- experiments;
- diagnostics;
- recovery;
- implementation status.

The engineering view should expose structure rather than hide it behind a simplified presentation.

## 4. AI / Machine presentation

An AI-facing implementation should provide stable machine-readable identifiers for the same interface areas.

Recommended top-level identifiers:

```text
organism
observation
architecture
graph
memory
history
experiments
organs
recovery
workspace
```

Each object should expose its identifier, type, status and available relationships where applicable.

## 5. Same organism, different presentation

```text
                    ORGANISM
                       │
          ┌────────────┼────────────┐
          │            │            │
        GUEST        OPERATOR    ENGINEER
          │            │            │
       explain       operate      build
          │            │            │
          └────────────┼────────────┘
                       │
                 same organism
```

The views are different windows into the same system. They are not separate versions of the organism.

## 6. Future UI

A graphical implementation may use:

- dashboard;
- navigation tree;
- organ cards;
- graph canvas;
- state timeline;
- experiment workspace;
- history browser;
- recovery console;
- AI interaction panel.

The exact visual design is intentionally left open until the interface model is sufficiently stable.
