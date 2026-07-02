---
document: AP-0004
title: Distributed by Default
status: Working Draft
maturity: Foundation
version: 0.1.0

category: Architectural Principle

editors:
  - Devinda Poodoo
  - OpenAI (Technical Editor)

created: 2026-07-01
updated: 2026-07-01

depends_on: []

related:
  - EAIA-0100

architectural_principles: []

design_goals:
  - DG-0003

audience:
  - Architects
  - Implementers

keywords:
  - decentralisation
  - peer-to-peer

license: Apache-2.0
---

# Status of This Document

Working Draft.

---

# Principle

The Ntangl architecture SHOULD favour distributed collaboration over centralised coordination wherever practical.

---

# Rationale

Distributed architectures improve resilience, reduce single points of failure and allow participants to collaborate across organisational boundaries.

Centralised services MAY be used where they provide operational benefit, but SHALL NOT become mandatory for routine collaboration.

---

# Implications

The architecture SHOULD support:

- direct peer-to-peer communication
- relay-assisted communication
- local decision making
- disconnected operation where feasible

---

# Related Documents

EAIA-0100

Relay Specification

---

# Change History

## 0.1.0

Initial Working Draft.
