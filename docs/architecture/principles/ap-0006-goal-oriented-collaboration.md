---
document: AP-0006
title: Mission Oriented Collaboration
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
  - AP-0001

related:
  - EAIA-0002

architectural_principles: []

design_goals:
  - DG-0001
  - DG-0002

audience:
  - Architects
  - Implementers

keywords:
  - goals
  - collaboration
  - planning

license: Apache-2.0
---

# Status of This Document

Working Draft.

---

# Principle

Collaboration SHALL be organised around shared operational goals rather than predefined workflows or static system integrations.

---

# Rationale

The purpose of collaboration is to achieve an operational outcome.

Participants should therefore coordinate around the desired result rather than the sequence of implementation steps.

This enables participants from different manufacturers and domains to contribute according to their capabilities and current operational context.

---

# Implications

Goals SHOULD be first-class architectural objects.

Participants MAY dynamically join or leave collaborations as goals evolve.

Task allocation SHOULD remain independent of implementation technology.

---

# Examples

Objective:

Deliver pallet A to loading bay 7.

Different participants MAY fulfil the objective using different:

- locomotion systems
- manipulation strategies
- navigation methods
- scheduling algorithms

provided the shared goal is achieved.

---

# Related Documents

EAIA-0002

Goal Protocol (reserved)

---

# Change History

## 0.1.0

Initial Working Draft.
