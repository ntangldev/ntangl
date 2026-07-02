---
document: AP-0009
title: Operational Separation of Concerns
status: Working Draft
maturity: Foundation
version: 0.1.0

category: Architectural Principle

editors:
  - Devinda Poodoo
  - OpenAI (Technical Editor)

created: 2026-07-01
updated: 2026-07-01

depends_on:
  - ADR-0004

related:
  - EAIA-0001
  - EAIA-0100
  - EAIA-0102

architectural_principles:
  - AP-0001
  - AP-0005
  - AP-0006

design_goals:
  - DG-0001
  - DG-0002
  - DG-0005
  - DG-0007

audience:
  - Architects
  - Protocol Designers
  - Implementers

keywords:
  - mission
  - goal
  - collaboration
  - task
  - capability
  - context

license: Apache-2.0
---

# Status of This Document

Working Draft.

---

# Principle

Ntangl SHALL preserve a clear separation between operational intent, operational outcomes, collaborative execution, work allocation, capabilities, and operational readiness.

---

# Rationale

Collaboration between heterogeneous Participants requires a shared model of work that avoids overloading any single architectural object.

The following separation provides the canonical operational model:

| Concept | Answers |
|----------|---------|
| Mission | Why does the work exist? |
| Goal | What must be achieved? |
| Collaboration | How do Participants work together? |
| Task | Who does what? |
| Capability | Who can do it? |
| Context | Who can do it now? |

This separation allows each concept to evolve independently while remaining composable within the overall architecture.

---

# Implications

Protocol specifications SHOULD preserve this separation.

Mission objects SHOULD NOT be used to describe task allocation.

Goal objects SHOULD NOT be used to encode governance beyond what is required to determine goal validity.

Capability objects SHOULD describe potential ability.

Context objects SHOULD describe current operational readiness.

Task allocation SHOULD occur within Collaboration Instances and remain constrained by Mission governance, Goal requirements, Participant Capability, and Participant Context.

---

# Examples

A warehouse Mission may exist to fulfil an order.

That Mission may contain Goals such as retrieving, transporting, and loading a pallet.

Participants collaborate to achieve those Goals.

Tasks are allocated to specific Participants based on Capability and Context.

---

# Related Documents

ADR-0004

EAIA-0100

EAIA-0102

---

# Change History

## 0.1.0

Initial Working Draft.
