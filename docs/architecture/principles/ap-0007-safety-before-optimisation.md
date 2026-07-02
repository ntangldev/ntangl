---
document: AP-0007
title: Safety Before Optimisation
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
  - EAIA-0002

architectural_principles: []

design_goals:
  - DG-0005

audience:
  - Architects
  - Safety Engineers

keywords:
  - safety
  - optimisation

license: Apache-2.0
---

# Status of This Document

Working Draft.

---

# Principle

No optimisation SHALL compromise operational safety.

---

# Rationale

Participants operate within the physical world.

Failures have physical consequences.

Performance improvements are valuable only when they preserve safe operation.

---

# Implications

Safety constraints SHALL take precedence over:

- efficiency
- throughput
- latency
- resource utilisation
- commercial objectives

Participants SHOULD refuse collaboration requests that violate local safety policy.

---

# Examples

A participant SHALL reject a task if:

- required safety clearances are unavailable
- environmental hazards exceed policy
- execution would violate local operational constraints

---

# Related Documents

Safety Protocol (reserved)

---

# Change History

## 0.1.0

Initial Working Draft.
