---
document: EAIA-0108
title: Architectural Taxonomy Model
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
  - EAIA-0100
  - EAIA-0102
  - EAIA-0103
  - EAIA-0104
  - EAIA-0105
  - EAIA-0106
  - EAIA-0107
  - EAIA-0199

related:
  - EAIP-0000

architectural_principles:
  - AP-0001
  - AP-0003
  - AP-0005
  - AP-0009
  - AP-0010

design_goals:
  - DG-0001
  - DG-0002
  - DG-0003
  - DG-0004
  - DG-0005
  - DG-0006
  - DG-0007

audience:
  - Architects
  - Standards Authors
  - Protocol Designers
  - SDK Developers
  - Implementers

keywords:
  - taxonomy
  - metamodel
  - architecture
  - semantics

license: Apache-2.0
---

# Status of This Document

This document is a Working Draft.

It defines the architectural taxonomy used throughout the Ntangl standards.

The taxonomy provides a conceptual classification of the architectural elements that comprise the Ntangl ecosystem.

---

# Abstract

The Ntangl architecture consists of multiple complementary categories of architectural elements.

This document establishes a common taxonomy for those elements.

The taxonomy is intended to improve consistency across standards, simplify future evolution and provide a common vocabulary for architects and implementers.

The taxonomy is conceptual.

It does not define protocol behaviour or implementation requirements.

---

# 1. Purpose

This document establishes the canonical architectural taxonomy for Ntangl.

The taxonomy SHALL:

- classify architectural concepts
- distinguish semantic entities from infrastructure
- distinguish architecture from protocols
- guide future standards development
- provide a common conceptual framework

---

# 2. Scope

This document applies to:

- EAIA architecture specifications
- EAIP protocol specifications
- reference implementations
- SDKs
- certification programmes
- implementation guidance

---

# 3. Taxonomy Principles

The taxonomy is intended to satisfy the following principles.

Architectural categories SHALL:

- possess clear responsibilities
- avoid overlap
- remain implementation independent
- support federation
- support extensibility

New architectural concepts SHOULD belong to an existing category.

Creation of new categories SHOULD require an Architecture Decision Record (ADR).

---

# 4. Architectural Taxonomy

The Ntangl architecture consists of four primary categories.

```text
Ntangl Architecture

├── Semantic Objects

├── Infrastructure Services

├── Protocol Artefacts

└── Specifications
```

Each category represents a distinct architectural concern.

---

# 5. Semantic Objects

Semantic Objects represent persistent concepts within the architecture.

Examples include:

- Mission
- Goal
- Collaboration
- Collaboration Instance
- Participant
- Capability
- Context
- Trust Relationship
- Policy
- Trust Domain

Semantic Objects:

- possess identity
- possess lifecycle
- possess state
- participate in interactions
- generate events

Semantic Objects are defined by EAIA-0102.

---

# 6. Infrastructure Services

Infrastructure Services enable collaboration between Semantic Objects.

Examples include:

- Discovery
- Relay
- Identity Resolution
- Object Resolution
- Trust Evaluation
- Policy Evaluation
- Event Distribution
- Audit

Infrastructure Services:

- provide capabilities
- preserve semantics
- are independently replaceable
- support federation

Infrastructure Services are defined by EAIA-0107.

---

# 7. Protocol Artefacts

Protocol Artefacts are exchanged between Participants.

Examples include:

- Object
- Command
- Response
- Event
- Query
- Document

Protocol Artefacts:

- have protocol representations
- support interoperability
- are transport independent
- preserve architectural semantics

Protocol Artefacts are defined by EAIP-0000.

---

# 8. Specifications

Specifications define the Ntangl standards.

The specification hierarchy consists of:

- EAIA Architecture
- EAIP Protocols
- Profiles
- Extensions
- Certification

Specifications are versioned independently.

---

# 9. Relationships

The taxonomy establishes the following relationships.

```text
Semantic Objects

↓

Interactions

↓

State Transitions

↓

Architectural Events

↓

Protocol Artefacts

↓

Infrastructure Services

↓

Transport
```

Each layer builds upon the previous layer.

Lower layers SHALL NOT redefine the semantics established by higher layers.

---

# 10. Evolution

Future architectural concepts SHOULD be introduced through:

1. Architecture Decision Record
2. Architectural Principle (if required)
3. EAIA specification
4. EAIP protocol representation

Protocol specifications SHALL NOT introduce new architectural semantics.

---

# 11. Conformance

Architecture Conformance SHALL preserve the taxonomy established by this document.

Protocol Conformance SHALL preserve the relationships between categories.

Certification MAY verify taxonomy compliance.

---

# 12. Design Guidance

When introducing a new concept, architects SHOULD determine:

- Is it a Semantic Object?
- Is it an Infrastructure Service?
- Is it a Protocol Artefact?
- Is it a Specification?

If none apply, an ADR SHOULD justify the introduction of a new architectural category.

---

# 13. Relationship to Other Models

The Architectural Taxonomy provides the highest-level conceptual view of Ntangl.

The remaining EAIA specifications refine specific aspects of the taxonomy.

| Specification | Responsibility |
|--------------|----------------|
| EAIA-0100 | Overall architecture |
| EAIA-0102 | Semantic Objects |
| EAIA-0103 | Operational State |
| EAIA-0104 | Interactions |
| EAIA-0105 | Events |
| EAIA-0106 | Identity, Identifier and Namespace |
| EAIA-0107 | Infrastructure Services |
| EAIA-0199 | Conformance |

---

# 14. Relationship to EAIP

The EAIP protocol suite provides interoperable representations of the taxonomy defined by this document.

EAIP specifications SHALL preserve the taxonomy.

EAIP specifications SHALL NOT redefine the taxonomy.

---

# Security Considerations

The taxonomy itself introduces no security mechanisms.

Security requirements are defined by the relevant EAIA and EAIP specifications.

---

# References

EAIA-0100 — Reference Architecture

EAIA-0102 — Architectural Object Model

EAIA-0103 — Operational State Model

EAIA-0104 — Architectural Interaction Model

EAIA-0105 — Architectural Event Model

EAIA-0106 — Identity, Identifier and Namespace Model

EAIA-0107 — Architectural Infrastructure Services Model

EAIA-0199 — Conformance Model

EAIP-0000 — Protocol Framework

RFC 2119

RFC 8174

---

# Change History

## 0.1.0

Initial Working Draft.

Established the canonical architectural taxonomy for the Ntangl standards.
