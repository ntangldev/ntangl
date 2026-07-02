---
document: AP-0005
title: Context Matters
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
  - AP-0002
  - AP-0003

related:
  - EAIA-0001
  - EAIA-0002

architectural_principles: []

design_goals:
  - DG-0001
  - DG-0004
  - DG-0005

audience:
  - Architects
  - Implementers
  - Protocol Designers

keywords:
  - context
  - collaboration
  - capability

license: Apache-2.0
---

# Status of This Document

Working Draft.

---

# Principle

Capabilities alone SHALL NOT determine whether a participant is suitable for collaboration.

Operational context SHALL be considered before commitments are made.

---

# Rationale

A participant's declared capabilities describe what it can do.

Operational context describes what it can do **now**.

A participant may possess the necessary capabilities while being temporarily unavailable because of:

- existing commitments
- energy constraints
- safety restrictions
- environmental conditions
- equipment availability
- communication limitations

Collaboration decisions that ignore operational context are likely to produce unreliable outcomes.

---

# Implications

Participants SHOULD expose sufficient operational context to allow informed collaboration decisions.

Participants MAY choose to withhold context according to local policy.

Context SHALL be considered transient and continuously evolving.

---

# Examples

A participant capable of lifting 100 kg MAY decline a lifting task because:

- battery level is below policy threshold
- it is already committed to a higher priority objective
- required tooling is unavailable
- environmental conditions prevent safe operation

---

# Related Documents

EAIA-0002

EAIP Context Protocol (reserved)

---

# Change History

## 0.1.0

Initial Working Draft.
