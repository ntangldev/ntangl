---
document: ADR-0001

title: Collaboration First

status: Accepted

version: 1.0.0

category: Architecture Decision

editors:
  - Devinda Poodoo
  - OpenAI (Technical Editor)

created: 2026-07-01
updated: 2026-07-01

depends_on: []

related:
  - EAIA-0000
  - EAIA-0002

architectural_principles:
  - AP-0001

design_goals:
  - DG-0001
  - DG-0007

keywords:
  - collaboration
  - architecture
  - lifecycle

license: Apache-2.0
---

# Status of This Document

This Architecture Decision has been **Accepted**.

Architecture Decisions are normative within the Ntangl standards repository.

---

# Abstract

This document establishes that collaboration, rather than communication, is the primary architectural concern of the Ntangl architecture.

All protocol specifications SHALL be designed to support the Collaborative Interaction Lifecycle.

---

# Context

Traditional networking protocols focus primarily on transporting information between endpoints.

While reliable communication is essential, communication alone does not enable meaningful collaboration between participants.

Participants must also:

- discover one another
- establish identity
- establish trust
- understand capabilities
- exchange operational context
- agree goals
- allocate work
- execute collaboratively
- monitor progress
- complete objectives safely

Communication exists only to support these higher-level activities.

---

# Decision

The Ntangl architecture SHALL adopt **Collaboration First** as a primary architectural principle.

The Collaborative Interaction Lifecycle SHALL become the canonical operational model for all protocol development.

Every protocol specification SHALL explicitly identify which stages of the lifecycle it supports.

No protocol SHALL exist without a clear relationship to the lifecycle.


## Operational Flexibility

The Collaborative Interaction Lifecycle (CIL) defines the canonical sequence of activities required to establish and complete collaboration between participants.

Implementations MAY optimise or combine individual stages of the lifecycle where equivalent security, safety and interoperability guarantees are preserved.

Such optimisations SHALL NOT alter the architectural intent of the lifecycle and SHALL remain interoperable with implementations that follow the canonical sequence.

The CIL therefore defines the reference model for collaboration rather than a mandatory message exchange sequence.
---

# Rationale

Designing protocols independently often leads to:

- duplicated functionality
- inconsistent behaviour
- proprietary integration
- fragmented implementations

Designing around collaboration ensures that protocol responsibilities remain coherent and aligned with operational objectives.

---

# Consequences

Identity protocols establish trusted participants.

Discovery protocols identify potential collaborators.

Capability protocols describe potential contributions.

Context protocols determine current operational readiness.

Goal protocols establish shared objectives.

Messaging protocols support execution.

Audit protocols record collaboration outcomes.

Future protocol specifications SHALL reference this Architecture Decision where appropriate.

---

# Alternatives Considered

## Communication First

Rejected.

Communication is necessary but not sufficient to achieve collaboration.

---

## Task Allocation First

Rejected.

Task allocation occurs only after identity, trust, capability and context have been established.

---

## Goal First

Rejected.

Goals cannot be evaluated without understanding participant capabilities and operational context.

---

# References

EAIA-0000 — The Embodied AI Internet Manifesto

EAIA-0002 — Collaborative Interaction Lifecycle

RFC 2119

RFC 8174

---

# Change History

## 1.0.0

Initial Accepted Architecture Decision.
