---
document: AP-0003
title: Trust is Earned
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
  - DG-0004

audience:
  - Security Engineers
  - Architects

keywords:
  - trust
  - security

license: Apache-2.0
---

# Status of This Document

Working Draft.

---

# Principle

Trust SHALL be established through verifiable evidence rather than assumed from manufacturer, network location or prior association.

---

# Rationale

Embodied AI participants frequently collaborate across organisational and operational boundaries.

Trust mechanisms must therefore be portable, verifiable and policy-driven.

---

# Implications

Trust evaluation SHOULD support:

- cryptographic verification
- policy evaluation
- delegation
- revocation
- cached trust assertions
- trust domain membership

Trust MAY be evaluated before, during or after identity verification depending upon deployment architecture, provided collaboration is established only after both identity and trust requirements have been satisfied.

---

# Related Documents

EAIP-0400 (Trust Architecture)

---

# Change History

## 0.1.0

Initial Working Draft.
