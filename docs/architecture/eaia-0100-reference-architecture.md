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

The Ntangl Reference Architecture defines the conceptual architecture for secure collaboration between autonomous Participants operating across organisational, technological and geographical boundaries.

Rather than prescribing implementation techniques, the architecture establishes the first-class architectural objects, their relationships and the interaction models required to enable interoperable collaboration.

Ntangl is fundamentally an architecture for collaboration. Communication, identity, trust and protocol exchange exist to support collaborative execution rather than constituting the architectural objective themselves.

The reference architecture provides the foundation upon which all Ntangl protocol specifications, reference implementations and certification programmes are built.

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

The architecture intentionally defines *what* interoperable systems are required to represent and accomplish, while avoiding unnecessary constraints on *how* those outcomes are implemented.

Implementation behaviour is specified by the EAIP protocol series.

---

# 2. Scope

The architecture defines the following first-class architectural objects:

* Mission
* Goal
* Collaboration
* Collaboration Instance
* Participant
* Capability
* Context
* Trust Relationship
* Policy
* Trust Domain
* Relay

The architecture also defines the relationships between these objects and the architectural principles governing their interaction.

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

## 3.1 Collaboration as the Primary Architectural Concern

The primary architectural concern of Ntangl is collaboration.

Communication, networking, identity, trust and policy exist to enable Participants to collaborate safely and effectively towards shared operational outcomes.

Consequently, the architecture is organised around operational intent, collaboration and execution rather than protocol layering alone.

This distinction separates Ntangl from traditional networking architectures, which primarily standardise communication rather than collaborative behaviour.

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

The Ntangl architecture is centred upon collaborative execution.

Mission provides operational intent.

Goals define measurable outcomes.

Collaboration provides the mechanism through which Participants cooperate to achieve those Goals.

Collaboration Instances represent the execution of collaborative activities.

Participants contribute Capabilities while continuously publishing operational Context.

Trust Relationships and Policies govern participation.

Relay services support communication where direct connectivity is unavailable.

The architecture deliberately separates governance, operational outcomes, collaborative execution and implementation concerns, allowing each to evolve independently while preserving interoperability.

---

# 7. First-Class Architectural Objects

The architecture defines the following first-class objects.

| Object                 | Purpose                                     |
| ---------------------- | ------------------------------------------- |
| Mission                | Operational intent and governance           |
| Goal                   | Measurable operational outcome              |
| Collaboration          | Coordinated activity                        |
| Collaboration Instance | Execution of collaborative behaviour        |
| Participant            | Network-visible collaborating entity        |
| Capability             | Potential ability                           |
| Context                | Current operational readiness               |
| Trust Relationship     | Evidence supporting collaboration decisions |
| Policy                 | Behavioural constraints                     |
| Trust Domain           | Administrative trust boundary               |

Architectural Infrastructure Services are defined separately in EAIA-0107.

These objects collectively define the semantic foundation of the Ntangl architecture.

Their detailed semantics are specified in **EAIA-0102 – Architectural Object Model**.

---

# 8. Object Relationships

The Ntangl architecture organises collaboration through the following conceptual hierarchy:

```text
                 Mission
                     │
                     ▼
                  Goal(s)
                     │
                     ▼
             Collaboration
                     │
                     ▼
        Collaboration Instance(s)
                     │
                     ▼
               Participant(s)
             ┌────────┴────────┐
             ▼                 ▼
        Capability         Context
             │
             ▼
           Policy

────────────────────────────────────────────

Architectural Infrastructure Services

• Discovery
• Relay
• Identity Resolution
• Object Resolution
• Trust Evaluation
• Policy Evaluation
• Event Distribution
• Audit
```

This hierarchy represents conceptual ownership and responsibility.

It SHALL NOT be interpreted as an implementation architecture or protocol message sequence.

Architectural Objects are semantic concepts that MAY be represented differently by different protocol specifications while preserving common architectural meaning.

---

## 8.1 Conceptual Pairing

The first-class architectural objects form complementary conceptual pairs that separate operational intent from execution.

| Intent     | Execution              |
| ---------- | ---------------------- |
| Mission    | Collaboration          |
| Goal       | Collaboration Instance |
| Capability | Context                |

These pairings are fundamental to the Ntangl architecture.

Mission defines *why* work exists.

Goal defines *what* must be achieved.

Collaboration defines *how* Participants cooperate.

Collaboration Instance defines *how collaboration is being executed at a specific point in time*.

Capability defines *what a Participant is capable of*.

Context defines *what a Participant is currently able to contribute*.

Maintaining this separation of concerns enables independent evolution of governance, planning, execution and operational state while preserving interoperability.

---

# 9. Collaboration

Collaboration is the operational mechanism through which Participants cooperate to achieve one or more Goals within the context of a Mission.

A Collaboration Instance represents the execution of collaborative behaviour by a specific group of Participants.

Participants MAY dynamically join or leave Collaboration Instances subject to applicable Mission governance, Policies and Trust Relationships.

The Collaborative Interaction Lifecycle defines the canonical operational model for establishing, executing and completing Collaboration Instances.

Implementations MAY optimise this lifecycle provided interoperability, security and safety are preserved.

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

* Architectural Object Model
* Layer Model
* Collaboration Model
* Identity Architecture
* Trust Architecture
* Mission Model
* Policy Model

The EAIP protocol specifications define interoperable representations and behaviours for the architectural concepts established by the EAIA series.


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
