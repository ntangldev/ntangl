---
document: AP-0002
title: Identity Before Interaction
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
  - EAIA-0001

architectural_principles: []

design_goals:
  - DG-0001
  - DG-0004

audience:
  - Architects
  - Security Engineers

keywords:
  - identity
  - authentication

license: Apache-2.0
---

# Status of This Document

Working Draft.

---

# Principle

Every participant MUST possess a verifiable identity before participating in collaboration.

---

# Rationale

Identity provides the foundation for trust, accountability and policy enforcement.

Without verifiable identity, secure collaboration cannot be established.

---

# Implications

Participants SHALL possess a verifiable identity before entering into collaborative commitments.

Identity evaluation MAY occur explicitly during collaboration establishment or implicitly through existing trust relationships, cached credentials or trust domain membership.

Regardless of implementation, participants SHALL be able to demonstrate a verifiable identity before collaboration proceeds beyond the establishment phase.

---

# Related Documents

EAIP-0100 (Identity Protocol)

---

# Change History

## 0.1.0

Initial Working Draft.
