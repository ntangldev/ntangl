---
document: AP-0001
title: Collaboration First
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
  - ADR-0001

related:
  - EAIA-0000
  - EAIA-0002

architectural_principles: []

design_goals:
  - DG-0001

audience:
  - Architects
  - Protocol Designers

keywords:
  - collaboration
  - lifecycle

license: Apache-2.0
---

# Status of This Document

Working Draft.

---

# Principle

The primary purpose of Ntangl is to enable secure collaboration between participants.

Communication is a supporting capability rather than the architectural objective.

---

# Rationale

Participants do not communicate for its own sake.

They communicate in order to achieve shared operational goals.

Therefore the architecture SHOULD optimise for collaboration rather than message transport.

---

# Implications

Protocols SHOULD support one or more stages of the Collaborative Interaction Lifecycle.

No protocol SHOULD exist without a clearly defined role within that lifecycle.

---

# Related Documents

ADR-0001

EAIA-0002

---

# Change History

## 0.1.0

Initial Working Draft.
