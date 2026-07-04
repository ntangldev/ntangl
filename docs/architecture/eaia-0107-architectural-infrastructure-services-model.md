---
document: EAIA-0107
title: Architectural Infrastructure Services Model
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

related:
  - EAIA-0199

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
  - Protocol Designers
  - SDK Developers
  - Implementers

keywords:
  - services
  - architecture
  - relay
  - discovery
  - federation

license: Apache-2.0
---

# Status of This Document

This document is a Working Draft.

It defines the Architectural Infrastructure Services that enable collaboration between Architectural Objects.

Architectural Infrastructure Services provide infrastructure capabilities.

They are not Architectural Objects.

---

# Abstract

The Ntangl architecture distinguishes between persistent semantic entities and the services that enable their discovery, interaction, governance and operation.

Architectural Objects represent the concepts that participate in collaboration.

Architectural Infrastructure Services provide the capabilities that support collaboration.

This separation enables implementations to evolve infrastructure independently while preserving architectural interoperability.

---

# 1. Purpose

This document establishes the canonical Architectural Infrastructure Services Model.

It defines:

- Architectural Infrastructure Services
- Service responsibilities
- Service characteristics
- Service interactions
- Service federation
- Service composition

---

# 2. Scope

This specification applies to all infrastructure capabilities that support the Ntangl architecture.

It intentionally excludes:

- protocol implementations
- deployment topologies
- software architectures
- operational procedures

---

# 3. Architectural Objects versus Architectural Infrastructure Services

Architectural Objects represent persistent semantic entities.

Examples include:

- Mission
- Goal
- Participant
- Capability
- Context
- Policy

Architectural Infrastructure Services provide infrastructure capabilities that enable those objects to collaborate.

Architectural Infrastructure Services SHALL NOT alter the semantic meaning of Architectural Objects.

---

# 4. Service Principles

Architectural Infrastructure Services SHALL:

- be implementation independent
- support federation
- preserve interoperability
- preserve object semantics
- be independently replaceable
- expose well-defined behaviours

Architectural Infrastructure Services SHOULD avoid becoming mandatory central authorities.

---

# 5. Service Characteristics

Architectural Infrastructure Services are typically:

- stateless or minimally stateful
- horizontally scalable
- replaceable
- independently deployable
- discoverable
- observable

Implementations MAY combine multiple services into a single runtime.

The architecture treats them as independent conceptual services.

---

# 6. Core Architectural Infrastructure Services

The Ntangl architecture defines the following core services.

| Service | Purpose |
|----------|----------|
| Discovery | Locate Participants and services |
| Relay | Assist communication where direct connectivity is unavailable |
| Identity Resolution | Resolve Architectural Identifiers |
| Trust Evaluation | Evaluate trust evidence |
| Policy Evaluation | Evaluate governance and operational policy |
| Event Distribution | Distribute Architectural Events |
| Object Resolution | Resolve Architectural Objects |
| Audit | Record observable architectural activity |

Additional services MAY be defined by future specifications.

---

# 7. Discovery Service

## Purpose

Enable Participants to discover other Participants and Architectural Infrastructure Services.

Discovery SHALL support federated environments.

Discovery SHALL NOT require a single global registry.

Discovery MAY utilise:

- peer-to-peer discovery
- relay-assisted discovery
- distributed registries
- multicast
- implementation-specific mechanisms

---

# 8. Relay Service

## Purpose

Relay assists communication when direct connectivity cannot be established.

Relay SHALL:

- preserve protocol semantics
- avoid modifying protocol content
- support federation
- minimise operational dependency

Relay SHALL NOT become an architectural authority.

Relay is an infrastructure capability rather than a semantic participant in collaboration.

---

# 9. Identity Resolution Service

Identity Resolution provides mechanisms for resolving Architectural Identifiers into protocol representations.

Resolution MAY return:

- object references
- current metadata
- endpoint information
- policy-controlled views

Resolution semantics are defined independently of protocol encoding.

---

# 10. Trust Evaluation Service

Trust Evaluation assesses available trust evidence.

Evaluation MAY consider:

- credentials
- historical behaviour
- delegated authority
- policy
- organisational relationships

Trust Evaluation SHALL remain independent of specific trust technologies.

---

# 11. Policy Evaluation Service

Policy Evaluation determines whether requested operations comply with applicable governance.

Policy evaluation MAY consider:

- Mission constraints
- organisational policy
- safety requirements
- regulatory requirements
- Participant context

Policy engines SHALL produce deterministic decisions.

---

# 12. Event Distribution Service

Event Distribution enables dissemination of Architectural Events.

Distribution MAY support:

- subscriptions
- filtering
- replay
- persistence
- federation

Distribution mechanisms are protocol-specific.

---

# 13. Object Resolution Service

Object Resolution provides access to Architectural Objects.

Resolution MAY support:

- retrieval
- version selection
- historical lookup
- policy-controlled visibility

Object Resolution SHALL preserve object semantics.

---

# 14. Audit Service

Audit records observable architectural behaviour.

Audit SHOULD support:

- traceability
- compliance
- diagnostics
- historical reconstruction
- certification

Audit records SHOULD reference Architectural Events whenever possible.

---

# 15. Service Composition

Architectural Infrastructure Services MAY cooperate.

Examples include:

Discovery

↓

Identity Resolution

↓

Trust Evaluation

↓

Policy Evaluation

↓

Object Resolution

↓

Relay

↓

Event Distribution

Service composition SHALL preserve interoperability.

---

# 16. Federation

Architectural Infrastructure Services SHALL support federation.

Federation SHALL NOT require:

- central ownership
- central administration
- global infrastructure

Independent administrative domains SHOULD interoperate through published standards.

---

# 17. Service Identifiers

Architectural Infrastructure Services MAY possess identifiers.

Service identifiers support:

- discovery
- auditing
- federation
- monitoring

Service identifiers SHALL NOT imply that services are first-class Architectural Objects.

---

# 18. Relationship to EAIP

The EAIA series defines Architectural Service semantics.

The EAIP series defines:

- service discovery protocols
- service interaction protocols
- service representations
- service security
- service interoperability

---

# Security Considerations

Architectural Infrastructure Services frequently process security-sensitive information.

Implementations SHOULD provide:

- authentication
- authorisation
- integrity protection
- confidentiality where appropriate
- auditability

Security mechanisms are defined by the EAIP protocol suite.

---

# References

EAIA-0100 — Reference Architecture

EAIA-0102 — Architectural Object Model

EAIA-0104 — Architectural Interaction Model

EAIA-0105 — Architectural Event Model

EAIA-0106 — Identity, Identifier and Namespace Model

EAIA-0199 — Conformance Model

RFC 2119

RFC 8174

---

# Change History

## 0.1.0

Initial Working Draft.

Established the Architectural Infrastructure Services Model and formally distinguished Architectural Infrastructure Services from Architectural Objects.
