---
document: EAIA-0104
title: Architectural Interaction Model
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

related:
  - ADR-0001
  - ADR-0003
  - ADR-0004

architectural_principles:
  - AP-0001
  - AP-0002
  - AP-0003
  - AP-0005
  - AP-0006
  - AP-0009

design_goals:
  - DG-0001
  - DG-0002
  - DG-0003
  - DG-0004
  - DG-0005

audience:
  - Architects
  - Protocol Designers
  - SDK Developers
  - Implementers

keywords:
  - interaction
  - collaboration
  - negotiation
  - lifecycle

license: Apache-2.0
---

# Status of This Document

This document is a Working Draft.

It defines the canonical architectural interaction patterns used throughout the Ntangl architecture.

Protocol message exchanges are specified by the EAIP series.

---

# Abstract

The Architectural Interaction Model defines the conceptual interactions between Architectural Objects during collaborative operation.

The model describes how Participants establish collaborative relationships, evaluate one another, cooperate towards shared Goals and conclude collaborative activity.

The interaction model intentionally describes behaviour rather than protocol implementation.

---

# 1. Purpose

This document establishes the canonical interaction semantics for Ntangl.

It defines:

- interaction patterns
- participant responsibilities
- interaction sequencing
- interaction ownership
- interaction outcomes

Protocol specifications SHALL preserve these semantics.

---

# 2. Scope

This document defines interactions involving:

- Missions
- Goals
- Collaboration
- Collaboration Instances
- Participants
- Capabilities
- Context
- Trust Relationships

It intentionally excludes:

- message formats
- transport protocols
- APIs
- implementation techniques

---

# 3. Interaction Principles

Architectural interactions SHALL:

- preserve interoperability
- preserve object semantics
- preserve auditability
- preserve policy
- preserve trust

Interactions MAY be implemented using different protocols provided observable behaviour remains consistent.

---

# 4. Primary Interaction Pattern

The primary interaction pattern within Ntangl is the Collaborative Interaction Lifecycle.

```text
Discover

↓

Identify

↓

Establish Trust

↓

Evaluate Capability

↓

Evaluate Context

↓

Join Collaboration

↓

Accept Task

↓

Execute

↓

Complete
```

This lifecycle represents the canonical collaboration model.

Implementations MAY optimise or combine individual stages provided interoperability, security and safety are preserved.

---

# 5. Interaction Types

The architecture defines several categories of interaction.

## Discovery

Locating potential Participants.

---

## Evaluation

Determining suitability through:

- identity
- trust
- capability
- context
- policy

---

## Negotiation

Establishing shared understanding regarding:

- participation
- responsibilities
- constraints
- expectations

---

## Collaboration

Coordinated activity towards one or more Goals.

---

## Delegation

Transferring operational responsibility between Participants.

---

## Monitoring

Observing progress throughout execution.

---

## Completion

Confirming successful completion of Goals and Collaboration Instances.

---

## Recovery

Restoring collaboration following interruption or failure.

---

## Withdrawal

Orderly departure of a Participant from active collaboration.

---

## Termination

Closing collaborative activity.

---

# 6. Interaction Ownership

Every interaction SHALL possess an initiating authority.

Depending upon context this MAY be:

- Mission owner
- Participant
- Policy engine
- Trust authority
- Collaboration coordinator

Ownership SHALL remain auditable.

---

# 7. Interaction Outcomes

Interactions produce one or more observable outcomes.

Typical outcomes include:

- object creation
- state transition
- trust establishment
- policy decision
- capability agreement
- context update
- collaboration establishment
- task allocation
- completion confirmation

---

# 8. Interaction Constraints

Interactions MAY be constrained by:

- Mission governance
- Goal dependencies
- Trust Relationships
- Participant Context
- Policies
- environmental conditions

Constraints SHALL be evaluated before commitments are made.

---

# 9. Interaction Failure

Interactions MAY fail.

Common reasons include:

- trust failure
- policy rejection
- unavailable capability
- unsuitable context
- communication failure
- timeout
- participant withdrawal

Failure SHALL preserve sufficient information for recovery and audit.

---

# 10. Interaction Recovery

Recovery MAY involve:

- retry
- renegotiation
- participant replacement
- goal reassignment
- mission update
- rollback

Recovery SHALL preserve object consistency.

---

# 11. Relationship to the Operational State Model

Interactions frequently result in state transitions.

The Operational State Model defines object lifecycle semantics.

The Architectural Interaction Model defines the activities that cause those transitions.

Protocol specifications SHALL preserve both models.

---

# 12. Relationship to EAIP

EAIA defines:

- architectural objects
- interaction semantics
- state semantics

EAIP defines:

- protocol operations
- messages
- validation
- event propagation

Protocol implementations SHALL preserve the architectural semantics defined by this document.

---

# Security Considerations

Interactions SHALL respect:

- identity
- trust
- policy
- Mission governance

Security mechanisms remain protocol-specific.

---

# References

EAIA-0100 — Reference Architecture

EAIA-0102 — Architectural Object Model

EAIA-0103 — Operational State Model

ADR-0001 — Collaboration First

ADR-0003 — Reference Models and Implementation Independence

ADR-0004 — Mission as a First-Class Architectural Object

RFC 2119

RFC 8174

---

# Change History

## 0.1.0

Initial Working Draft.

Established the canonical interaction semantics for the Ntangl architecture.
