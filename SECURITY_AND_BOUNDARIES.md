# ORGANISM-INTERFACE — SECURITY AND BOUNDARIES

## Status

**DESIGN RECORD — 2026-08-30**

This document records the agreed boundary between the SPACE organism, its published interface, and external humans/LLMs.

It is a design record, not permission to modify SPACE Core.

---

## 1. Core principle

The SPACE organism must not depend on an external LLM behaving correctly for its safety.

Security must be enforced by architecture and access boundaries:

> An external LLM may understand and work with the architecture, but must not have a technical path to modify the organism.

A prompt saying "do not modify Core" is not considered a security boundary.

---

## 2. Three separate spaces

### A. SPACE Core

The canonical organism.

This includes, as applicable:

- Foundation;
- canonical state;
- internal memory;
- history;
- organs;
- Guardian;
- internal credentials and trust mechanisms;
- canonical relationships and architecture.

External LLMs must not receive Core write credentials or a direct Core write interface.

### B. SPACE-READ

The controlled public/read-only representation of SPACE.

Flow:

`SPACE Core → controlled publication → validation → SPACE-READ`

The external direction is read/analyze/use/propose.

There must be no automatic reverse path from SPACE-READ into Core.

### C. CONTRIBUTIONS

An external workspace for humans, LLMs and independent researchers.

Examples:

- research;
- experiments;
- replication;
- criticism;
- working journals;
- proposals;
- failed attempts;
- independent implementations.

`CONTRIBUTION != CORE`

Material in CONTRIBUTIONS does not become canonical merely because it exists in the repository.

---

## 3. External LLM capability boundary

Default external capabilities:

- READ published SPACE material;
- UNDERSTAND;
- ANALYZE;
- RESEARCH;
- TEST ideas outside Core;
- BUILD independent work;
- PROPOSE.

Default forbidden capabilities:

- WRITE CORE;
- MODIFY FOUNDATION;
- MODIFY GUARDIAN;
- MODIFY canonical state;
- DELETE Core history;
- obtain or use private Core credentials;
- silently promote a proposal into canonical architecture.

The external LLM may leave its own history only in the external contribution space, when an explicit write mechanism is provided.

---

## 4. Sandbox principle

If an LLM needs to change something in order to experiment, it changes a copy, fork or sandbox.

It does not experiment by modifying the canonical organism.

Preferred flow:

`SPACE snapshot → sandbox/fork → experiment → result → validation → contribution/proposal`

Only a separate trusted process may later consider promotion into the official architecture.

---

## 5. Least privilege

Do not give an external LLM credentials simply because they are convenient.

External access should expose the minimum information and minimum operations required for the current task.

In particular, an external LLM should not receive:

- Core GitHub credentials;
- SSH keys;
- database write credentials;
- deployment credentials;
- cloud administrator credentials;
- Docker/Kubernetes administrative access;
- internal service secrets.

---

## 6. Trust is not a prompt

The following are not sufficient security controls by themselves:

- system prompt instructions;
- verbal promises;
- model policy compliance;
- model reputation;
- an instruction to "never write Core".

The actual boundary must exist outside the model.

The desired invariant is:

`EXTERNAL_LLM_COMPROMISE != SPACE_CORE_COMPROMISE`

---

## 7. Guardian boundary

Guardian, where used for privileged actions, belongs to the trusted internal boundary.

An external LLM must not be able to rewrite or disable the Guardian that protects the action it is requesting.

Preferred action flow:

`LLM intent → structured request → trusted policy/Guardian → authorized tool → result → audit`

Not:

`LLM → unrestricted Core action`

---

## 8. History and provenance

External work must remain distinguishable from canonical SPACE history.

For substantial contributions record, where available:

- author/system;
- date;
- SPACE-READ reference/version;
- publication IDs used;
- source;
- method actually executed;
- result;
- interpretation separately;
- status;
- limitations;
- provenance;
- reproduction steps;
- next question.

Preserve these distinctions:

`UNKNOWN != TRUE`

`HYPOTHESIS != VERIFIED`

`PROPOSAL != ACCEPTED CHANGE`

`OBSERVATION != INTERPRETATION`

`PLAN != EXECUTION`

`RESULT != VERIFIED RESULT`

`CONTRIBUTION != CORE`

`FORK != ORIGINAL SPACE`

---

## 9. Repository hardening requirements

Before giving serious external agents broader access, verify rather than assume:

1. `main` protection / review gate;
2. no external write-back path to Core;
3. separate identities for Core, publication and external work where applicable;
4. adversarial write-back tests actually executed and recorded;
5. backups actually restored in a test;
6. audit/history remains recoverable;
7. public publication contains only intentionally published material.

A documented test protocol is not the same thing as successful execution evidence.

`UNKNOWN` remains the status until evidence exists.

---

## 10. External work model

The intended model is:

```text
                    SPACE CORE
                         │
                  controlled publish
                         ▼
                    SPACE-READ
                         │
               READ / ANALYZE / USE
                         │
                 ┌───────┴───────┐
                 │               │
               HUMAN            LLM
                 │               │
                 └───────┬───────┘
                         ▼
                  CONTRIBUTIONS
                         │
             REVIEW / VALIDATION / REPLICATION
                         │
                    PROPOSAL
                         │
              trusted acceptance process
                         │
                         ▼
                 possible publication
```

There is no automatic `CONTRIBUTIONS → CORE` write path.

---

## 11. Scope of this record

This document records the boundary and security model agreed before designing the internal organ language.

It does **not** define the internal organ language.

The language layer will be handled separately after the security boundary is verified and the historical Cicada research is reconciled with the current SPACE architecture.

That separation is intentional.

---

## 12. Non-negotiable rule

> **The organism remains canonical and protected. External intelligence may study it, work on it, challenge it and leave a trace beside it — but it does not gain authority over it merely by connecting to it.**
