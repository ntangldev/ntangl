---
document: EAIA-0105
title: Architectural Event Model
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
  - DG-0006

audience:
  - Architects
  - Protocol Designers
  - SDK Developers
  - Implementers

keywords:
  - events
  - event model
  - state transition
  - observability
  - audit

license: Apache-2.0
---

# Status of This Document

This document is a Working Draft.

It defines the canonical Architectural Event Model for the Ntangl architecture.

Protocol event formats and transport mechanisms are defined by the EAIP protocol series.

---

# Abstract

The Architectural Event Model defines how significant changes within the Ntangl architecture are represented as immutable architectural events.

Architectural Events provide a common semantic model for audit, observability, coordination and historical analysis.

Events describe facts.

They do not describe intent.

---

# 1. Purpose

The purpose of this document is to establish a uniform event model for Ntangl.

The Architectural Event Model SHALL:

- define event semantics
- distinguish commands from events
- define event ownership
- define event ordering
- define event relationships
- support auditability
- support interoperability

---

# 2. Scope

This document defines events relating to Architectural Objects.

Architectural Infrastructure Services MAY generate operational events, but those events are infrastructure observations rather than semantic Architectural Events unless explicitly defined by a future specification.

---

# 3. Architectural Events

An Architectural Event is an immutable statement describing something that has occurred within the architecture.

Events SHALL describe facts.

Events SHALL NOT express intent.

Events SHALL NOT request behaviour.

---

# 4. Commands and Events

Commands and Events represent different architectural concepts.

| Command | Event |
|----------|-------|
| expresses intent | records fact |
| requests change | confirms change |
| may succeed or fail | has already occurred |
| may be rejected | immutable |

Examples:

Command:

```
Approve Goal
```

Event:

```
GoalApproved
```

Command:

```
Join Collaboration
```

Event:

```
ParticipantJoinedCollaboration
```

---

# 5. Event Principles

Architectural Events SHALL be:

- immutable
- timestamped
- attributable
- auditable
- versioned
- uniquely identifiable

Events SHALL NOT be modified after publication.

Corrections SHALL be represented by subsequent events.

---

# 6. Event Categories

The architecture recognises several categories of events.

## Lifecycle Events

Examples:

- MissionCreated
- GoalDefined
- ParticipantRegistered

---

## State Events

Examples:

- GoalApproved
- MissionCompleted
- ParticipantVerified

---

## Collaboration Events

Examples:

- CollaborationEstablished
- ParticipantJoined
- ParticipantWithdrew

---

## Trust Events

Examples:

- TrustEstablished
- TrustRevoked
- TrustExpired

---

## Capability Events

Examples:

- CapabilityPublished
- CapabilityWithdrawn

---

## Context Events

Examples:

- ContextUpdated
- ContextExpired

---

## Policy Events

Examples:

- PolicyApplied
- PolicyViolated

---

## Infrastructure Events

Examples:

- RelayConnected
- RelayDisconnected

---

# 7. Event Relationships

Events SHALL reference the Architectural Object to which they relate.

Events MAY reference:

- parent Mission
- associated Goal
- Collaboration Instance
- Participant
- Trust Domain

Events MAY establish causal relationships with previous events.

---

# 8. Event Ordering

Events SHOULD preserve causal ordering where practical.

The architecture SHALL NOT require globally synchronised clocks.

Ordering MAY be established using:

- logical clocks
- vector clocks
- causality identifiers
- implementation-specific mechanisms

Protocol specifications SHALL define interoperable ordering semantics.

---

# 9. Event Ownership

Every event SHALL identify the authority responsible for producing it.

Examples include:

- Participant
- Mission Owner
- Policy Engine
- Trust Authority
- Relay

Ownership SHALL remain auditable.

---

# 10. Event Persistence

Architectural Events MAY be retained for:

- audit
- observability
- diagnostics
- analytics
- compliance
- replay

Retention policies are implementation-specific.

---

# 11. Event Replay

Replay MAY be used to reconstruct historical object state.

Replay SHALL preserve chronological consistency.

Replay SHALL NOT modify historical events.

Replay behaviour is protocol-specific.

---

# 12. Event Security

Events SHALL preserve:

- integrity
- authenticity
- attribution

Events MAY additionally provide:

- confidentiality
- access control
- selective disclosure

Security mechanisms remain protocol-specific.

---

# 13. Relationship to the Operational State Model

State transitions describe changes to Architectural Objects.

Architectural Events provide immutable evidence that those transitions occurred.

Every observable state transition SHOULD result in one or more Architectural Events.

---

# 14. Relationship to the Interaction Model

Interactions describe collaborative behaviour.

Interactions frequently produce state transitions.

State transitions produce Architectural Events.

The relationship is therefore:

```
Interaction

↓

State Transition

↓

Architectural Event
```

---

# 15. Relationship to EAIP

The EAIA series defines event semantics.

The EAIP series defines:

- event representations
- event transport
- subscriptions
- filtering
- delivery guarantees
- acknowledgement

Protocol specifications SHALL preserve the semantics defined by this document.

---

# Security Considerations

Architectural Events SHALL be treated as authoritative evidence of system behaviour.

Implementations SHOULD ensure that events are resistant to tampering and unauthorised modification.

Security mechanisms remain protocol-specific.

---

# References

EAIA-0100 — Reference Architecture

EAIA-0102 — Architectural Object Model

EAIA-0103 — Operational State Model

EAIA-0104 — Architectural Interaction Model

ADR-0001 — Collaboration First

ADR-0003 — Reference Models and Implementation Independence

ADR-0004 — Mission as a First-Class Architectural Object

RFC 2119

RFC 8174

---

# Change History

## 0.1.0

Initial Working Draft.

Established the Architectural Event Model and the distinction between Commands and Events.
