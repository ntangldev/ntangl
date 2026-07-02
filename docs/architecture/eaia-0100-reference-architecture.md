---
document: EAIA-0100
title: Ntangl Reference Architecture
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
  - ADR-0001
  - ADR-0002
  - ADR-0003

related:
  - EAIA-0001
  - EAIA-0102

architectural_principles:
  - AP-0001
  - AP-0002
  - AP-0003
  - AP-0004
  - AP-0005
  - AP-0006
  - AP-0007
  - AP-0008

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
  - Implementers
  - Standards Bodies

keywords:
  - architecture
  - collaboration
  - interoperability

license: Apache-2.0
---

# Status of This Document

This document is a **Working Draft**.

It defines the conceptual architecture of Ntangl.

This document is informative.

Normative protocol behaviour is defined by the EAIP specification series.

---

# Abstract

The Ntangl Reference Architecture defines the conceptual model for secure collaboration between autonomous participants operating across organisational, technological and geographical boundaries.

Rather than prescribing implementation techniques, this architecture establishes the architectural objects, relationships and interaction patterns required to enable interoperable collaboration.

The reference architecture serves as the foundation for all Ntangl protocol specifications, reference implementations and certification programmes.

---

# 1. Purpose

The purpose of the Ntangl Reference Architecture is to provide a stable conceptual framework for the development of interoperable collaboration standards.

The architecture SHALL:

- establish common terminology
- define the principal architectural objects
- describe their relationships
- identify architectural boundaries
- define collaboration at an architectural level
- provide a stable foundation for protocol development

The architecture intentionally avoids prescribing implementation techniques.

---

# 2. Scope

The architecture defines:

- Participants
- Identity
- Trust
- Goals
- Capabilities
- Context
- Collaboration
- Trust Domains
- Relay Services

The architecture does not define:

- transport protocols
- AI models
- planning algorithms
- perception systems
- operating systems
- hardware
- networking technologies

Those concerns are addressed by implementation-specific technologies and future protocol specifications.

---

# 3. Architectural Objectives

Ntangl exists to enable secure, vendor-neutral collaboration.

The architecture pursues the following objectives:

- interoperability
- scalability
- resilience
- decentralisation
- extensibility
- security
- safety
- vendor neutrality

These objectives are realised through the Architectural Principles and Design Goals defined elsewhere within the repository.

---

# 4. Architectural Constraints

The architecture has been developed under the following assumptions.

## 4.1 Heterogeneous Participants

Participants will be developed by different manufacturers using different hardware, software and AI technologies.

The architecture SHALL remain implementation independent.

---

## 4.2 Distributed Operation

Participants SHOULD operate without dependence upon central coordination whenever practical.

Central infrastructure MAY exist but SHALL NOT become mandatory for normal collaboration.

---

## 4.3 Long Operational Lifetimes

Industrial and infrastructure deployments may remain operational for decades.

The architecture SHOULD favour stability over short-term optimisation.

---

## 4.4 Trust Boundaries

Participants frequently operate across organisational boundaries.

Identity, trust and policy SHALL therefore remain first-class architectural concerns.

---

# 5. Architectural Principles

The architecture is governed by the Architectural Principles defined within the AP document series.

The principles are intentionally stable and SHOULD evolve infrequently.

Every protocol specification SHOULD identify the principles that it implements.

---

# 6. Reference Architecture

The Ntangl architecture is centred upon collaboration rather than communication.

Communication is an enabling capability.

Collaboration is the architectural objective.

Every collaboration consists of a collection of Participants working towards one or more shared Goals.

Participants establish trust relationships, exchange capabilities and operational context, allocate responsibilities and coordinate execution.

This interaction is independent of manufacturer, deployment technology and implementation language.

---

# 7. First-Class Architectural Objects

The architecture defines the following first-class objects.

| Object | Purpose |
|----------|----------|
| Mission | Authorised unit of work initiated by a requestor |
| Participant | Network-visible collaborator |
| Goal | Desired operational outcome |
| Capability | Declared ability |
| Context | Current operational state |
| Collaboration | Coordinated activity |
| Collaboration Instance | A specific execution of collaboration |
| Trust Relationship | Evidence supporting interaction |
| Policy | Rules governing behaviour |
| Trust Domain | Administrative trust boundary |
| Relay | Infrastructure service supporting connectivity |

These objects form the common vocabulary of the architecture.

Detailed definitions are provided in EAIA-0102.

---

# 8. Object Relationships

At a conceptual level:

- Missions define one or more goals
- Goals define a desired outcome
- Collaboration Instances exist to achieve one or more Goals.
- Participants belong to one or more Trust Domains.
- Participants possess Capabilities.
- Participants maintain operational Context.
- Participants participate in Collaboration Instances.
- Capabilities
- Context

The architecture intentionally avoids prescribing implementation mechanisms for these relationships.

---

# 9. Collaboration

Missions define the operational intent

Goals define desired outcomes

Collaboration provides the mechanism through which Participants cooperate to achieve those goals

Collaboration Instances represent specific executions of that collaboration

---

# 10. Trust Boundaries

Trust is evaluated within one or more Trust Domains.

Trust Domains define administrative, organisational or operational boundaries within which policy decisions may be shared.

Participants MAY belong to multiple Trust Domains simultaneously.

The architecture does not require a global trust authority.

---

# 11. Architectural Views

The Ntangl architecture may be considered through several complementary viewpoints.

## Collaboration View

How Participants cooperate to achieve Goals.

## Information View

How architectural objects relate to one another.

## Trust View

How identity, trust and policy influence collaboration.

## Deployment View

How Participants, Relays and infrastructure are distributed across physical environments.

Each viewpoint represents the same architecture from a different perspective.

---

# 12. Relationship to EAIP

The EAIA series defines architectural concepts.

The EAIP series defines protocol behaviour.

Protocols SHALL implement the architecture.

Protocols SHALL NOT redefine architectural concepts.

---

# 13. Security Considerations

Security is fundamental to collaboration.

Identity, trust and policy SHALL be established before collaborative commitments are accepted.

Security mechanisms SHALL remain implementation independent.

Detailed protocol behaviour is defined by the EAIP series.

---

# 14. Extensibility

The architecture has been designed to accommodate future participant types, deployment environments and collaboration models.

New protocols, capabilities and services MAY be introduced without modifying the core architectural concepts defined by this document.

---

# 15. Future Work

Subsequent architecture documents expand upon:

- Architectural Object Model
- Layer Model
- Collaboration Model
- Identity Architecture
- Trust Architecture

The EAIP protocol specifications define interoperable behaviour implementing these concepts.

---

# References

EAIA-0000 — The Embodied AI Internet Manifesto

EAIA-0001 — Glossary

ADR-0001 — Collaboration First

ADR-0002 — Documentation Standards

ADR-0003 — Reference Models and Implementation Independence

RFC 2119

RFC 8174

---

# Change History

## 0.1.0

Initial Working Draft.

Established the conceptual reference architecture for the Ntangl Standards Repository.
