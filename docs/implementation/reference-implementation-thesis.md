---
document: RI-0001
title: Reference Implementation Thesis
status: Working Draft
maturity: Foundation
version: 0.1.0

category: Implementation

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
  - EAIA-0108
  - EAIA-0199
  - EAIP-0000
  - EAIP-0001

license: Apache-2.0
---

# Status of This Document

This document is informative.

It describes the architectural philosophy and technology choices proposed for the first Ntangl reference implementation.

It is not a normative specification.

Implementations are not required to follow this document in order to conform to the Ntangl standards.

---

# Abstract

The Ntangl standards intentionally separate architecture from implementation.

This document describes a reference implementation that demonstrates the architectural principles using a fully decentralised, peer-to-peer design.

The implementation philosophy emphasises:

- decentralisation
- replaceable layers
- semantic interoperability
- distributed ownership
- implementation independence

The technologies described in this document represent current implementation preferences rather than mandatory standards.

---

# 1. Vision

The reference implementation aims to demonstrate that large-scale collaboration between autonomous participants can be achieved without requiring central ownership, central coordination or proprietary infrastructure.

Every participant is intended to operate as an equal member of a federated ecosystem.

The architecture assumes that trust is established through protocol and policy rather than organisational ownership.

---

# 2. Architectural Philosophy

The implementation follows several core principles.

## Peer-to-Peer First

Communication should occur directly between participants whenever possible.

Infrastructure should assist communication rather than control it.

---

## Federation by Default

No participant should require membership of a single global service.

Multiple organisations should be able to collaborate while retaining operational independence.

---

## Replaceable Layers

Every architectural layer should be independently replaceable.

No implementation technology should become architecturally mandatory.

---

## Semantic Interoperability

Participants should exchange meaning rather than implementation-specific structures.

The semantic model should remain stable while implementation technologies evolve.

---

## Local Autonomy

Each participant should retain control over:

- execution
- storage
- identity
- trust
- policy
- decision making

---

# 3. Reference Architecture

The proposed implementation consists of independently replaceable layers.

```text
Applications

↓

Ntangl SDK

↓

EAIP Protocols

↓

Semantic Object Layer

↓

Distributed Knowledge Layer

↓

Distributed Runtime

↓

Transport

↓

Network
```

Each layer communicates only through published interfaces.

---

# 4. Network Layer

The preferred network architecture is fully peer-to-peer.

Characteristics include:

- direct connectivity
- NAT traversal
- encrypted communication
- relay fallback
- decentralised addressing

The current preferred implementation is:

**iroh**

Alternative implementations remain valid provided EAIP semantics are preserved.

---

# 5. Transport Layer

The transport layer provides reliable message exchange.

Responsibilities include:

- connection establishment
- fragmentation
- retransmission
- flow control
- encryption

Transport technology is intentionally isolated from higher architectural layers.

---

# 6. Distributed Runtime

The runtime coordinates collaboration between participants.

Responsibilities include:

- execution
- scheduling
- synchronisation
- replication
- conflict handling

The runtime should remain transport independent.

---

# 7. Distributed Knowledge Layer

The canonical knowledge representation is an RDF Dataset.

Each participant contributes one or more Named Graphs.

```text
Dataset

├── Default Graph

├── Named Graph (Participant A)

├── Named Graph (Participant B)

├── Named Graph (Participant C)

└── ...
```

The dataset represents shared semantic knowledge rather than shared application state.

---

# 8. RDF as the Semantic Foundation

The preferred semantic representation is RDF 1.1.

Reasons include:

- global identifiers
- semantic interoperability
- graph composition
- distributed ownership
- existing standards
- mature tooling

Architectural Objects map naturally onto RDF resources.

Relationships become RDF predicates.

Architectural Events become immutable graph additions.

---

# 9. Named Graph Ownership

Named Graphs represent participant ownership.

Each participant is responsible for maintaining its own Named Graph.

Participants SHOULD NOT directly modify another participant's graph.

Collaboration emerges through linked graphs rather than shared ownership.

This model supports provenance, auditability and decentralised governance.

---

# 10. Validation

The preferred validation technologies are:

- SHACL
- ShEx

Validation responsibilities include:

- object integrity
- relationship integrity
- policy validation
- capability validation
- context validation

Validation should occur before protocol state transitions.

---

# 11. Architectural Objects

Architectural Objects SHOULD be represented as RDF resources.

Examples include:

- Mission
- Goal
- Participant
- Capability
- Context
- Policy

Object representations should remain independent of storage implementation.

---

# 12. Documents

External artefacts SHOULD be referenced rather than embedded.

Examples include:

- CAD models
- BIM
- maps
- images
- procedures
- datasets

Documents remain independently managed.

---

# 13. Shared Mission Code

Mission participants frequently require identical operational behaviour.

The reference implementation therefore introduces the concept of a **Mission Package**.

A Mission Package contains the executable artefacts required for participation in a Mission.

Typical contents include:

- workflow definitions
- policies
- validation rules
- executable code
- schemas
- configuration
- assets

The concept is inspired by Holochain hApps while remaining implementation independent.

The architecture does not prescribe a package format.

---

# 14. Distributed Reactive Behaviour

The reference implementation proposes modelling distributed execution using reactive rules operating over the shared semantic graph.

Reactive rules:

- observe graph changes
- evaluate constraints
- generate Commands
- publish Events
- update local state

Execution remains distributed.

No global scheduler is required.

---

# 15. Spatial Collaboration

The preferred spatial model is based upon Bigraphs with Sharing.

Bigraphs provide:

- spatial containment
- connectivity
- mobility
- dynamic topology

Rather than embedding Bigraph semantics directly into the architecture, the reference implementation proposes mapping Bigraph structures onto RDF.

This enables:

- semantic querying
- graph validation
- event generation
- protocol interoperability

---

# 16. Semantic Mapping

Higher-level implementation models SHOULD map onto RDF rather than replace it.

Examples include:

- Bigraphs
- workflow models
- mission plans
- capability ontologies
- policy models

RDF remains the canonical semantic representation.

Higher-level models become specialised views.

---

# 17. Layer Isolation

Every implementation layer should be independently replaceable.

Possible future substitutions include:

| Layer | Possible Alternatives |
|--------|-----------------------|
| Transport | QUIC, DDS, MQTT, HTTP |
| Semantic Layer | RDF, LPG, future graph models |
| Validation | SHACL, ShEx, future constraint languages |
| Runtime | Multiple implementations |
| Storage | Triple store, embedded graph, distributed database |

Replacing one layer SHALL NOT require changes to architectural semantics.

---

# 18. Relationship to the Standards

The reference implementation demonstrates one possible implementation of the Ntangl standards.

It is expected to evolve alongside the standards.

Normative requirements remain defined exclusively by the EAIA and EAIP specification series.

---

# 19. Research Areas

The following areas remain active research topics:

- distributed reasoning
- graph synchronisation
- semantic conflict resolution
- distributed rule execution
- mission package distribution
- graph versioning
- provenance
- decentralised identity
- trust propagation
- spatial reasoning

Future implementations may adopt different solutions while remaining conformant.

---

# 20. Future Evolution

The reference implementation is expected to evolve continuously.

Changes to implementation technologies should not require changes to the architectural standards.

Where implementation experience identifies improvements to the architecture, those changes should be introduced through the Architecture Decision Record (ADR) process before being incorporated into the EAIA series.

---

# References

EAIA-0100 — Reference Architecture

EAIA-0102 — Architectural Object Model

EAIA-0107 — Architectural Infrastructure Services Model

EAIA-0108 — Architectural Taxonomy Model

EAIA-0199 — Conformance Model

EAIP-0000 — Protocol Framework

EAIP-0001 — Common Message Model

---

# Change History

## 0.1.0

Initial Working Draft.

Established the engineering philosophy and preferred technology stack for the first Ntangl reference implementation while preserving implementation independence.
