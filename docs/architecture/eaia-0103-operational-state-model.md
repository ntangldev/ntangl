---
document: EAIA-0103
title: Operational State Model
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

related:
  - ADR-0001
  - ADR-0003
  - ADR-0004

architectural_principles:
  - AP-0001
  - AP-0005
  - AP-0006
  - AP-0009

design_goals:
  - DG-0001
  - DG-0002
  - DG-0003
  - DG-0005

audience:
  - Architects
  - Protocol Designers
  - SDK Developers
  - Implementers

keywords:
  - state
  - lifecycle
  - execution
  - architecture

license: Apache-2.0
---

# Status of This Document

This document is a Working Draft.

It defines the canonical operational state model used throughout the Ntangl architecture.

Normative protocol behaviour is specified by the EAIP protocol series.

---

# Abstract

The Operational State Model defines the common lifecycle semantics used by all first-class architectural objects within Ntangl.

Rather than prescribing object-specific state machines, this document establishes a common vocabulary for state, transitions, ownership, audit and recovery.

Individual architectural objects specialise this model while preserving consistent behavioural semantics across the architecture.

---

# 1. Purpose

The purpose of this document is to provide a uniform operational state model for the Ntangl architecture.

The Operational State Model SHALL:

- define common lifecycle semantics
- define state transition terminology
- define transition ownership
- define transition constraints
- define recovery principles
- define audit expectations

All architectural object lifecycles SHOULD conform to this model.

---

# 2. Scope

This document applies to every first-class architectural object including:

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
- Relay

---

# 3. Operational State Principles

Operational state describes the current condition of an architectural object.

Operational state SHALL be:

- observable
- deterministic
- auditable
- recoverable
- versioned

Operational state SHALL NOT redefine the semantic meaning of an architectural object.

---

# 4. Uniform State Model

Every architectural object SHOULD progress through the following conceptual lifecycle.

```text
Created

↓

Validated

↓

Authorised

↓

Active

↓

Suspended

↓

Resumed

↓

Completed

↓

Archived
```

Not every object is required to implement every state.

Object-specific lifecycles MAY specialise this model.

---

# 5. State Definitions

## Created

The object exists but has not yet been validated.

---

## Validated

The object has passed structural and semantic validation.

---

## Authorised

The object has been approved for operational use according to applicable policy.

---

## Active

The object is participating in normal operation.

---

## Suspended

Operational activity has been temporarily paused.

State SHALL be preserved.

---

## Resumed

Operational activity continues after suspension.

---

## Completed

The operational purpose of the object has been fulfilled.

---

## Archived

The object is retained for historical, audit or analytical purposes.

No further operational changes are expected.

---

# 6. State Transition Principles

Transitions SHALL:

- preserve consistency
- be deterministic
- be auditable
- respect policy
- preserve security

Transitions MAY be rejected.

Rejected transitions SHALL provide a reason.

---

# 7. Transition Ownership

Every state transition SHALL have an authoritative initiator.

Examples include:

- Mission owner
- Participant owner
- Collaboration leader
- Policy engine
- Trust authority

Ownership MAY be delegated.

Delegation SHALL remain auditable.

---

# 8. Transition Constraints

Transitions MAY depend upon:

- policy
- trust
- capability
- context
- mission governance
- goal dependencies

Constraints SHALL be evaluated before transition completion.

---

# 9. Failure Handling

Objects MAY enter exceptional conditions.

Examples include:

- validation failure
- authorisation failure
- timeout
- cancellation
- communication failure

Failure SHALL preserve sufficient information for recovery or audit.

---

# 10. Recovery

Recovery mechanisms SHOULD minimise disruption.

Recovery MAY involve:

- retry
- rollback
- revalidation
- reassignment
- manual intervention

Recovery SHALL preserve audit history.

---

# 11. Audit

Every state transition SHOULD generate an audit event.

Audit records SHOULD include:

- object identifier
- previous state
- new state
- timestamp
- initiator
- reason
- policy decisions
- trust evidence

---

# 12. Object Lifecycle Profiles

Individual architectural objects specialise the Uniform State Model.

Examples include:

Mission

```text
Created
↓

Published
↓

Authorised
↓

Active
↓

Completed
↓

Archived
```

Goal

```text
Defined
↓

Approved
↓

Active
↓

Satisfied
↓

Verified
↓

Closed
```

Participant

```text
Registered
↓

Verified
↓

Available
↓

Collaborating
↓

Unavailable
↓

Retired
```

Collaboration

```text
Proposed
↓

Established
↓

Executing
↓

Completed
↓

Closed
```

These profiles preserve common lifecycle semantics while allowing domain-specific terminology.

---

# 13. Relationship to EAIP

The EAIA series defines conceptual lifecycle semantics.

The EAIP series defines:

- protocol operations
- state transition messages
- transition validation
- event propagation
- error handling

EAIP specifications SHALL preserve the lifecycle semantics established by this document.

---

# 14. Extensibility

Additional lifecycle states MAY be introduced by future architectural objects.

Extensions SHALL:

- preserve interoperability
- preserve auditability
- preserve deterministic behaviour

Extensions SHALL NOT redefine the common lifecycle semantics.

---

# Security Considerations

State transitions SHALL respect:

- identity
- trust
- policy
- mission governance

Unauthorised state transitions SHALL be rejected.

---

# References

EAIA-0100 — Reference Architecture

EAIA-0102 — Architectural Object Model

ADR-0001 — Collaboration First

ADR-0003 — Reference Models and Implementation Independence

ADR-0004 — Mission as a First-Class Architectural Object

RFC 2119

RFC 8174

---

# Change History

## 0.1.0

Initial Working Draft.

Established the Uniform Operational State Model for the Ntangl architecture.
