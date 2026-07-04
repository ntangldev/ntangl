---
document: AP-INDEX
title: Architectural Principles Index
status: Working Draft
maturity: Foundation
version: 0.1.0

category: Architecture

editors:
  - Devinda Poodoo
  - OpenAI (Technical Editor)

created: 2026-07-01
updated: 2026-07-01

depends_on:
  - EAIA-0000

related:
  - ADR-0001
  - ADR-0002

architectural_principles: []

design_goals: []

audience:
  - Architects
  - Contributors

keywords:
  - principles

license: Apache-2.0
---

# Status of This Document

This document indexes the Architectural Principles that underpin the Ntangl architecture.

---

# Purpose

Architectural Principles describe the enduring design philosophy of Ntangl.

Every normative specification SHOULD reference one or more Architectural Principles.

These principles evolve slowly and provide the rationale for architectural and protocol decisions.

---

# Ntangl Architectural Principles

The Architectural Principles define the enduring design philosophy of the Ntangl architecture.

Unlike protocol specifications, Architectural Principles are intended to remain stable across multiple generations of protocols and implementations.

Every EAIA and EAIP specification SHOULD reference the relevant Architectural Principles.

---

# Structural Principles

Structural Principles define the organisation of the architecture and the relationships between architectural concepts.

| ID      | Title                              | Status        |
| ------- | ---------------------------------- | ------------- |
| AP-0001 | Architecture Before Implementation | Working Draft |
| AP-0003 | Protocol Independence              | Working Draft |
| AP-0009 | Operational Separation of Concerns | Working Draft |
| AP-0010 | Identifiability                    | Working Draft |

---

# Behavioural Principles

Behavioural Principles define how architectural elements evolve and cooperate throughout their lifecycle.

| ID      | Title                          | Status        |
| ------- | ------------------------------ | ------------- |
| AP-0005 | Persistent Identity            | Working Draft |
| AP-0006 | Mission-Oriented Collaboration | Working Draft |

---

# Quality Principles

Quality Principles define the characteristics expected of the architecture and its implementations.

| ID      | Title                               | Status        |
| ------- | ----------------------------------- | ------------- |
| AP-0002 | Interoperability by Design          | Working Draft |
| AP-0004 | Security by Design                  | Working Draft |
| AP-0007 | Extensibility Without Fragmentation | Working Draft |
| AP-0008 | Implementation Independence         | Working Draft |

---

# Relationship to the EAIA Series

The Architectural Principles provide normative design guidance for the Ntangl architecture.

The Reference Architecture (EAIA-0100) defines the overall structure.

The Architectural Principles explain the design philosophy that underpins that structure.

The Architectural Object Model (EAIA-0102), Operational State Model (EAIA-0103), Architectural Interaction Model (EAIA-0104), Architectural Event Model (EAIA-0105), and Identity, Identifier and Namespace Model (EAIA-0106) apply these principles to specific aspects of the architecture.

---

# Evolution

Architectural Principles are expected to evolve slowly.

New principles SHOULD only be introduced where they provide enduring architectural guidance that cannot reasonably be expressed through existing principles or Architecture Decision Records (ADRs).

Changes to Architectural Principles SHOULD be supported by an accepted ADR before being incorporated into the standards.

---

# Normative References

* EAIA-0100 — Reference Architecture
* EAIA-0102 — Architectural Object Model
* EAIA-0199 — Conformance Model

---

# Informative References

* ADR-0001 — Collaboration First
* ADR-0002 — Documentation Standards
* ADR-0003 — Reference Models and Implementation Independence
* ADR-0004 — Mission as a First-Class Architectural Object

---

# Change History

## 0.1.0

Initial Working Draft.
