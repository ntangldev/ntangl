---
document: ADR-0004
title: Mission as a First-Class Architectural Object
status: Accepted
maturity: Foundation
version: 1.0.0

category: Architecture Decision

editors:
  - Devinda Poodoo
  - OpenAI (Technical Editor)

created: 2026-07-01
updated: 2026-07-01

depends_on:
  - ADR-0001
  - ADR-0002
  - ADR-0003

related:
  - EAIA-0000
  - EAIA-0001
  - EAIA-0100
  - EAIA-0102

architectural_principles:
  - AP-0001
  - AP-0005
  - AP-0006
  - AP-0009

design_goals:
  - DG-0001
  - DG-0002
  - DG-0005
  - DG-0007

audience:
  - Architects
  - Protocol Designers
  - Implementers
  - Standards Bodies

keywords:
  - mission
  - goals
  - collaboration
  - governance
  - architecture

license: Apache-2.0
---

# Status of This Document

This Architecture Decision has been **Accepted**.

Architecture Decisions are normative within the Ntangl Standards Repository.

---

# Abstract

This Architecture Decision establishes **Mission** as a first-class architectural object within the Ntangl Reference Architecture.

A Mission provides the authoritative description of operational intent, governance, constraints and success criteria for collaborative activities.

Goals, Collaboration Instances and Participant activities exist within the context of a Mission.

---

# Context

Earlier revisions of the architecture modelled collaboration directly around Goals.

While this approach adequately described operational outcomes, it did not provide an architectural object representing:

- operational intent
- requesting authority
- governance
- ownership
- priorities
- lifecycle management
- success criteria

As a consequence, Goals risked becoming overloaded with responsibilities unrelated to their primary purpose.

---

# Decision

Mission SHALL be introduced as a first-class architectural object.

A Mission represents the authoritative definition of an operational objective together with the governance necessary to achieve it.

Goals SHALL represent measurable operational outcomes contributing to the completion of a Mission.

Collaboration SHALL provide the mechanism through which Participants cooperate to achieve one or more Goals.

Collaboration Instances SHALL represent individual executions of collaboration associated with one or more Goals.

---

# Architectural Model

The high-level architectural hierarchy becomes:

```text
Mission
    │
    ├── Goal(s)
    │       │
    │       └── Collaboration Instance(s)
    │                    │
    │                    └── Participant(s)
    │                              │
    │                              ├── Capability
    │                              ├── Context
    │                              └── Policy
    │
    └── Success Criteria
```

---

# Responsibilities

## Mission

A Mission defines:

- operational intent
- requesting authority
- governance
- constraints
- priorities
- success criteria
- associated Goals

A Mission defines **why** work exists.

---

## Goal

Goals define:

- measurable outcomes
- completion criteria
- dependencies

Goals define **what** must be achieved.

---

## Collaboration

Collaboration defines:

- cooperative behaviour
- participant coordination
- information exchange
- agreement mechanisms

Collaboration defines **how Participants work together**.

---

## Collaboration Instance

A Collaboration Instance represents a specific execution of collaborative activity associated with one or more Goals.

Multiple Collaboration Instances MAY contribute to the same Goal.

---

## Participant

Participants contribute Capabilities toward one or more Goals while operating within Mission constraints and local policy.

---

# Rationale

Separating Mission from Goal provides several architectural benefits.

## Separation of Concerns

Operational governance remains independent from operational execution.

---

## Scalability

Large Missions MAY contain multiple Goals executed by multiple Collaboration Instances operating concurrently.

---

## Flexibility

Participants MAY dynamically join or leave Collaboration Instances without changing Mission intent.

---

## Traceability

Operational decisions can be traced from:

Mission

↓

Goals

↓

Collaboration Instances

↓

Participant Actions

This provides a natural audit model.

---

## Extensibility

Future protocol specifications may extend Mission metadata without affecting Goal or Collaboration semantics.

---

# Examples

## Warehouse

Mission

Fulfil Customer Order #48231

Goals

- Retrieve pallet
- Deliver pallet
- Confirm loading

Collaboration Instances

- Retrieval team
- Transport team
- Loading team

---

## Hospital

Mission

Prepare Operating Theatre

Goals

- Sterilise equipment
- Position equipment
- Verify readiness

---

## Lunar Surface Operations

Mission

Deploy Solar Array

Goals

- Transport equipment
- Assemble supports
- Connect power systems
- Verify operation

---

# Consequences

The following architectural changes SHALL be made.

The glossary SHALL define Mission as a first-class architectural object.

The Reference Architecture SHALL include Mission within the architectural object model.

Goal SHALL be redefined as a measurable operational outcome contributing to a Mission.

Collaboration SHALL operate within the context of one or more Goals.

Future protocol specifications SHALL support Mission-aware collaboration.

---

# Alternatives Considered

## Goal as the Top-Level Object

Rejected.

Goals represent operational outcomes rather than operational governance.

---

## Workflow as the Top-Level Object

Rejected.

Workflows prescribe implementation behaviour and are not sufficiently flexible for heterogeneous collaboration.

---

## Task as the Top-Level Object

Rejected.

Tasks represent implementation details rather than architectural concepts.

---

# References

ADR-0001 — Collaboration First

ADR-0002 — Documentation Standards

ADR-0003 — Reference Models and Implementation Independence

EAIA-0000 — The Embodied AI Internet Manifesto

EAIA-0001 — Glossary

EAIA-0100 — Ntangl Reference Architecture

EAIA-0102 — Architectural Object Model

---

# Change History

## 1.0.0

Initial Accepted Architecture Decision.

Established Mission as a first-class architectural object and defined the separation between operational intent, operational outcomes and collaborative execution.
