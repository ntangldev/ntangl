---
document: EAIA-0102
title: Architectural Object Model
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
  - ADR-0004

related:
  - EAIA-0001

architectural_principles:
  - AP-0001
  - AP-0002
  - AP-0003
  - AP-0004
  - AP-0005
  - AP-0006
  - AP-0007
  - AP-0008
  - AP-0009

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
  - object model
  - architecture
  - collaboration

license: Apache-2.0
---

# Status of This Document

This document is a Working Draft.

It defines the canonical architectural objects used throughout the Ntangl Reference Architecture.

Protocol specifications SHALL reference these objects rather than redefining them.

---

# Abstract

The Ntangl Architectural Object Model defines the semantic objects that form the foundation of the Ntangl architecture.

These objects describe the concepts exchanged, referenced and manipulated during collaboration between Participants.

Architectural Objects are conceptual entities.

They are independent of protocol encoding, implementation language and deployment architecture.

---

# 1. Purpose

The purpose of this document is to establish a common semantic model for the Ntangl architecture.

Every protocol specification SHALL reference these objects.

This document intentionally avoids defining protocol message formats.

---

# 2. Scope

This document defines the following first-class Architectural Objects:

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

Architectural Infrastructure Services are defined separately in **EAIA-0107**.

---

# 3. Architectural Objects

Architectural Objects represent persistent concepts within the Ntangl architecture.

They are:

- uniquely identifiable
- implementation independent
- protocol independent
- extensible
- versionable

Architectural Objects SHALL NOT be interpreted as protocol messages.

Protocols transport representations of Architectural Objects.

---

# 4. Object Relationships

The canonical object hierarchy is:

```text
Mission
    │
    ├── Goal(s)
    │       │
    │       └── Collaboration Instance(s)
    │                    │
    │                    └── Participant(s)
    │                              │
    │                              ├── Capability
    │                              ├── Context
    │                              └── Policy
    │
    └── Success Criteria
```

This hierarchy describes conceptual ownership.

It does not prescribe implementation.

---

# 5. Common Object Characteristics

Unless explicitly stated otherwise, every Architectural Object possesses the following characteristics.

## Identifier

Every object SHALL possess a globally unique identifier.

The identifier format is protocol independent.

---

## Version

Objects MAY evolve over time.

Version information SHOULD accompany persistent objects.

---

## Ownership

Every object SHALL possess an authoritative owner.

Ownership MAY be delegated.

---

## Lifecycle

Every object SHALL possess a defined lifecycle.

Lifecycle transitions MAY be constrained by policy.

---

## Security

Objects MAY possess confidentiality, integrity and authenticity requirements.

Security requirements are defined by protocol specifications.

---

## Extensibility

Implementations MAY extend objects with additional metadata.

Extensions SHALL NOT modify the semantic meaning defined by this document.

---

# 6. Mission

## Purpose

A Mission represents the authoritative description of operational intent.

Mission answers:

**Why does this work exist?**

---

## Responsibilities

Mission defines:

- operational intent
- requesting authority
- governance
- priorities
- constraints
- success criteria
- associated Goals

Mission does not define implementation.

---

## Ownership

Mission ownership belongs to the requesting authority.

Ownership MAY be transferred according to policy.

---

## Relationships

Mission owns:

- Goals
- Success Criteria

Mission constrains:

- Collaboration
- Participants

Mission references:

- Policies

---

## Lifecycle

Typical lifecycle:

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

Alternative lifecycles MAY exist.

---

## Identifier

Recommended identifier prefix:

```
MIS-
```

Protocol specifications define encoding.

---

## Security

Mission integrity SHALL be protected.

Mission modification SHALL require authorisation.

---

## Extensibility

Mission metadata MAY include:

- scheduling
- location
- budgeting
- compliance
- customer information

provided architectural semantics remain unchanged.

---

# 7. Goal

## Purpose

A Goal represents a measurable operational outcome contributing to completion of a Mission.

Goal answers:

**What must be achieved?**

---

## Responsibilities

Goals define:

- desired outcome
- completion criteria
- dependencies
- priority

Goals do not define implementation.

---

## Relationships

Goals belong to one Mission.

Goals MAY depend upon other Goals.

Goals MAY require multiple Collaboration Instances.

---

## Lifecycle

Typical lifecycle:

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

---

## Identifier

Recommended identifier prefix:

```
GOL-
```

---

## Security

Goal completion SHALL be verifiable.

Goal modification SHALL require authorisation.

---

## Extensibility

Goals MAY include:

- deadlines
- tolerances
- quality metrics
- domain-specific metadata

---

# 8. Collaboration

## Purpose

Collaboration represents coordinated behaviour between Participants.

Collaboration answers:

**How do Participants work together?**

---

## Responsibilities

Collaboration establishes:

- coordination
- communication
- agreement
- cooperation

Collaboration does not allocate work.

---

## Relationships

Collaboration exists to achieve Goals.

Collaboration contains one or more Collaboration Instances.

---

## Lifecycle

```text
Proposed

↓

Established

↓

Active

↓

Suspended

↓

Resumed

↓

Completed
```

---

## Identifier

Recommended identifier prefix:

```
COL-
```

---

## Security

Collaboration SHALL occur only between trusted Participants operating under compatible policies.

---

## Extensibility

Collaboration models MAY evolve without changing the architectural object.

---

# 9. Collaboration Instance

## Purpose

A Collaboration Instance represents one execution of collaborative activity.

It answers:

**How is this collaboration being executed right now?**

---

## Responsibilities

A Collaboration Instance manages:

- participating Participants
- current execution state
- allocated Tasks
- progress

---

## Relationships

Instances belong to Collaboration.

Instances contribute to Goals.

Instances involve Participants.

---

## Lifecycle

```text
Created

↓

Participants Joined

↓

Executing

↓

Monitoring

↓

Completed

↓

Closed
```

---

## Identifier

Recommended identifier prefix:

```
CLI-
```

---

## Security

Membership changes SHOULD be authorised.

Audit records SHOULD be maintained.

---

## Extensibility

Execution-specific metadata MAY be attached.

---

# 10. Participant

## Purpose

A Participant represents a network-visible identity capable of collaboration.

Participant answers:

**Who is participating?**

---

## Responsibilities

Participants:

- establish identity
- establish trust
- declare capabilities
- publish context
- accept commitments
- participate in collaboration

---

## Relationships

Participants possess:

- Capabilities
- Context
- Policies

Participants belong to one or more Trust Domains.

Participants contribute to Collaboration Instances.

---

## Lifecycle

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

---

## Identifier

Recommended identifier prefix:

```
PAR-
```

---

## Security

Participant identity SHALL be verifiable.

Trust SHALL be established before collaborative commitments are accepted.

---

## Extensibility

Participants MAY represent:

- individual embodiments
- coordinated fleets
- distributed systems
- future implementation models

provided they satisfy the architectural definition of a Participant.

---

# 11. Capability

## Purpose

A Capability represents a declared ability that a Participant MAY perform under appropriate operational conditions.

Capability answers:

**What can this Participant do?**

Capabilities describe potential ability rather than current availability.

---

## Responsibilities

Capabilities define:

- functional abilities
- supported operations
- operating constraints
- performance characteristics
- required resources
- optional prerequisites

Capabilities SHALL NOT describe current operational state.

Operational state is represented by Context.

---

## Relationships

Capabilities belong to one or more Participants.

Capabilities MAY contribute to one or more Goals.

Capabilities MAY require:

- specific equipment
- environmental conditions
- software modules
- certifications
- permissions

Capabilities MAY be referenced during collaboration planning and task allocation.

---

## Lifecycle

Typical lifecycle:

```text
Defined

↓

Verified

↓

Published

↓

Available

↓

Deprecated

↓

Retired
```

Capability availability remains independent of Capability existence.

---

## Identifier

Recommended identifier prefix:

```
CAP-
```

Protocol specifications define identifier encoding.

---

## Security

Capability declarations SHOULD be authentic.

Participants MAY selectively disclose Capabilities according to local policy.

Capability assertions MAY require independent verification.

---

## Extensibility

Capability descriptions MAY include:

- manufacturer extensions
- domain-specific metadata
- certification references
- semantic classifications
- performance metrics

Extensions SHALL preserve the architectural meaning of Capability.

---

# 12. Context

## Purpose

Context represents the current operational state of a Participant relevant to collaboration.

Context answers:

**What can this Participant do now?**

Context is dynamic.

Unlike Capability, Context is expected to change throughout normal operation.

---

## Responsibilities

Context describes operational readiness including, but not limited to:

- availability
- workload
- health
- energy state
- location
- environmental suitability
- communication status
- tooling availability

Context SHALL NOT redefine Participant identity or Capability.

---

## Relationships

Context belongs to exactly one Participant.

Context influences:

- trust decisions
- task allocation
- collaboration planning
- execution monitoring

Context MAY reference:

- Policies
- Capabilities
- Trust Domains

---

## Lifecycle

Typical lifecycle:

```text
Created

↓

Published

↓

Updated

↓

Superseded

↓

Expired
```

Unlike most Architectural Objects, Context is expected to evolve continuously.

Consumers SHOULD assume Context becomes stale unless refreshed.

---

## Identifier

Recommended identifier prefix:

```
CTX-
```

Individual Context updates MAY possess independent identifiers.

Protocol specifications define update semantics.

---

## Security

Context MAY contain sensitive operational information.

Participants SHALL retain control over Context disclosure.

Policies MAY restrict:

- visibility
- granularity
- update frequency
- recipients

Integrity protection SHOULD be provided for Context exchanged during collaboration.

---

## Extensibility

Context MAY include additional domain-specific information including:

- environmental sensors
- inventory status
- medical readiness
- logistics information
- mission-specific state

Such extensions SHALL NOT alter the architectural meaning of Context.

---

# 13. Trust Relationship

## Purpose

A Trust Relationship represents evidence supporting collaboration decisions between Participants.

Trust Relationship answers:

**Why should these Participants trust one another?**

Trust is represented as evidence rather than assumption.

---

## Responsibilities

Trust Relationships provide evidence relating to:

- identity verification
- credential validation
- policy compliance
- delegated authority
- historical interactions
- organisational relationships

Trust Relationships SHALL support evaluation without requiring a single global trust authority.

---

## Relationships

Trust Relationships MAY exist between:

- Participant ↔ Participant
- Participant ↔ Trust Domain
- Trust Domain ↔ Trust Domain

Trust Relationships influence:

- collaboration establishment
- policy evaluation
- task acceptance
- information sharing

Trust Relationships do not replace identity.

Identity and Trust remain separate architectural concepts.

---

## Lifecycle

Typical lifecycle:

```text
Established

↓

Verified

↓

Active

↓

Reviewed

↓

Revoked

↓

Archived
```

Trust MAY expire naturally according to policy.

Trust MAY be re-established through subsequent interactions.

---

## Identifier

Recommended identifier prefix:

```
TRU-
```

Protocol specifications SHALL define trust assertion formats.

---

## Security

Trust Relationships SHALL provide integrity protection.

Trust evidence SHOULD be independently verifiable.

Implementations SHOULD support:

- revocation
- expiry
- delegation
- auditability

Trust evaluation policies remain implementation-specific.

---

## Extensibility

Trust models MAY evolve independently of the architecture.

Examples include:

- Public Key Infrastructure (PKI)
- Web of Trust
- Verifiable Credentials
- Zero Trust architectures
- Organisation-specific trust frameworks

Ntangl intentionally does not mandate a single trust model.

Future protocol specifications SHALL define interoperable representations of trust evidence while preserving implementation independence.

---
Infrastructure capabilities that support these Architectural Objects are defined by **EAIA-0107 – Architectural Infrastructure Services Model** and are intentionally excluded from the Architectural Object Model.

---

# References

EAIA-0100

ADR-0004

EAIA-0001

---

# Change History

## 0.1.0

Initial Working Draft.

Defined the semantic model for the five primary architectural objects.
