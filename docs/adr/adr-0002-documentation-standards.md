---
document: ADR-0002
title: Documentation Standards
status: Accepted
maturity: Foundation
version: 1.0.0

category: Architecture Decision

editors:
  - Devinda Poodoo
  - OpenAI (Technical Editor)

created: 2026-07-01
updated: 2026-07-01

depends_on:
  - ADR-0001

related:
  - EAIA-0000

architectural_principles:
  - AP-0001

design_goals:
  - DG-0001

audience:
  - Architects
  - Protocol Designers
  - Contributors

keywords:
  - documentation
  - standards
  - governance

license: Apache-2.0
---

# Status of This Document

This Architecture Decision has been **Accepted**.

Architecture Decisions are normative within the Ntangl Standards Repository.

---

# Abstract

This document establishes the documentation standards for the Ntangl Standards Repository.

The repository SHALL be treated as the authoritative specification of the Ntangl architecture. All documentation SHALL follow a common structure, use consistent terminology and remain traceable to architectural principles and design goals.

---

# Context

Ntangl is intended to evolve as an open standards initiative.

As the project grows, architectural consistency becomes increasingly important. Without common documentation conventions, protocol specifications become difficult to review, maintain and implement consistently.

---

# Decision

All standards documents SHALL:

- use Markdown as the canonical source format
- include standard YAML metadata
- maintain semantic version numbers
- include document status
- include change history
- reference related documents where appropriate
- identify applicable Architectural Principles
- identify applicable Design Goals

Normative specifications SHALL use the terminology defined by RFC 2119 and RFC 8174.

---

# Metadata Requirements

Every standards document SHALL contain metadata describing:

- document identifier
- title
- status
- maturity
- version
- editors
- dates
- dependencies
- related documents
- architectural principles
- design goals
- audience
- keywords
- license

---

# Document Categories

The repository defines the following document classes.

| Prefix | Description |
|----------|-------------|
| EAIA | Embodied AI Internet Architecture |
| EAIP | Embodied AI Interoperability Protocol |
| ADR | Architecture Decision Record |
| AP | Architectural Principle |
| DG | Design Goal |
| RM | Reference Model |
| CERT | Certification |
| IG | Implementation Guide |

---

# Consequences

The documentation corpus becomes the authoritative definition of the Ntangl architecture.

Every protocol specification becomes traceable back to:

- architectural principles
- design goals
- architecture decisions

---

# References

ADR-0001

RFC 2119

RFC 8174

---

# Change History

## 1.0.0

Initial Accepted Architecture Decision.
