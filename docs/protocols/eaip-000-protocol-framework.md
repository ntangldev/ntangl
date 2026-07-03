---
document: EAIP-0000
title: Protocol Framework
status: Working Draft
maturity: Foundation
version: 0.1.0

category: Protocol Specification

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
  - EAIA-0199

related:
  - ADR-0001
  - ADR-0002
  - ADR-0003
  - ADR-0004

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
  - Protocol Designers
  - SDK Developers
  - Implementers
  - Certification Bodies

keywords:
  - protocol
  - framework
  - eaip
  - commands
  - events
  - queries
  - objects

license: Apache-2.0
---

# Status of This Document

This document is a Working Draft.

It defines the common framework for the EAIP protocol suite.

All EAIP protocol specifications SHALL conform to this framework unless explicitly superseded by a later accepted specification.

---

# Abstract

EAIP is the protocol suite implementing the architectural semantics defined by the EAIA series.

This document establishes the common protocol model for EAIP, including artefact classes, protocol responsibilities, operation types, conformance expectations, and the separation between architectural semantics and protocol representation.

EAIP protocols do not define new architectural concepts.

They define interoperable ways to represent, exchange, validate, observe, and transition the architectural objects defined by EAIA.

---

# 1. Purpose

The purpose of this document is to define the common foundation for all EAIP protocol specifications.

EAIP-0000 SHALL establish:

- the relationship between EAIA and EAIP
- the common artefact classes used by the protocol suite
- the common protocol operation model
- the distinction between Commands, Events, Queries, Objects, and Documents
- shared conformance expectations
- baseline protocol design constraints

---

# 2. Scope

This document applies to all EAIP specifications.

It defines protocol framework semantics only.

It does not define:

- message envelope formats
- serialization formats
- transport bindings
- cryptographic algorithms
- object-specific protocol operations
- certification procedures

Those concerns are defined by later EAIP, CERT, and implementation guide documents.

---

# 3. Relationship to EAIA

EAIA defines the architecture.

EAIP defines protocol behaviour.

EAIP specifications SHALL preserve the semantics of:

- EAIA-0100 Reference Architecture
- EAIA-0102 Architectural Object Model
- EAIA-0103 Operational State Model
- EAIA-0104 Architectural Interaction Model
- EAIA-0105 Architectural Event Model
- EAIA-0199 Conformance Model

EAIP specifications SHALL NOT redefine architectural objects.

EAIP specifications MAY define representations of architectural objects.

---

# 4. Protocol Philosophy

EAIP is designed around interoperable collaboration.

Communication is a supporting mechanism.

EAIP protocols SHALL support the creation, observation, exchange, validation, and state transition of architectural objects.

EAIP protocols SHOULD be independent of transport technology.

EAIP protocols SHOULD be usable across direct peer-to-peer, relay-assisted, and mediated deployments.

---

# 5. Protocol Artefact Classes

EAIP recognises five primary artefact classes.

| Artefact | Purpose |
|----------|---------|
| Object | Persistent architectural entity |
| Command | Request to perform an action or cause a state transition |
| Event | Immutable fact recording something that occurred |
| Query | Request for information without state change |
| Document | External supporting artefact referenced by the protocol |

These artefact classes SHALL be used consistently across the EAIP suite.

---

# 6. Object

An Object is a protocol representation of an Architectural Object defined by EAIA-0102.

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
- Relay

Objects represent persistent semantic entities.

Objects MAY be created, read, updated, archived, referenced, or observed according to protocol-specific rules.

EAIP specifications SHALL preserve the architectural semantics of represented Objects.

---

# 7. Command

A Command expresses intent.

A Command requests that a Participant, service, or authority perform an operation.

Commands MAY succeed, fail, be rejected, expire, or be cancelled.

Commands SHALL NOT be treated as facts.

Examples include:

- CreateMission
- ApproveGoal
- JoinCollaboration
- PublishCapability
- UpdateContext
- RevokeTrust

A Command SHOULD identify:

- command identifier
- command type
- target object
- initiating authority
- requested operation
- timestamp
- correlation identifier
- authorisation context

Command formats are defined by object-specific EAIP specifications.

---

# 8. Event

An Event records fact.

An Event is an immutable statement that something occurred.

Events SHALL NOT request behaviour.

Events SHALL NOT be modified after publication.

Corrections SHALL be represented by subsequent Events.

Examples include:

- MissionCreated
- GoalApproved
- ParticipantVerified
- CapabilityPublished
- ContextUpdated
- CollaborationEstablished
- TrustRevoked

An Event SHOULD identify:

- event identifier
- event type
- related object
- producing authority
- timestamp
- causal relationship
- correlation identifier
- previous state
- resulting state

Event semantics are defined by EAIA-0105.

Event formats are defined by later EAIP specifications.

---

# 9. Query

A Query requests information without requesting state change.

Queries SHALL NOT directly modify architectural object state.

Examples include:

- GetMission
- ListGoals
- ResolveParticipant
- DiscoverCapabilities
- QueryContext
- FindCollaborations

A Query MAY return:

- Objects
- Events
- summaries
- references
- errors
- empty results

Queries MAY be subject to policy, trust, privacy, and access control constraints.

---

# 10. Document

A Document is an external supporting artefact referenced by EAIP but not governed directly by the architectural object model.

Documents MAY include:

- maps
- CAD files
- BIM models
- manuals
- procedures
- safety documents
- inspection reports
- medical records
- digital twin data
- media files
- certificates
- datasets

EAIP SHALL NOT require ownership of Document contents.

EAIP MAY define mechanisms to reference Documents securely.

Document references SHOULD support:

- identity
- integrity verification
- access control
- versioning
- provenance
- retention policy

Documents are supporting artefacts.

They are not Architectural Objects unless explicitly represented as such by a future EAIA specification.

---

# 11. Operation Model

EAIP protocols generally perform one or more of the following operation classes.

## Create

Create a new Object.

## Read

Retrieve or resolve an Object.

## Update

Modify an Object or request a valid state transition.

## Archive

Mark an Object as no longer operationally active while retaining historical meaning.

## Observe

Subscribe to or retrieve Events relating to an Object.

## Query

Request information without state change.

## Reference

Associate an Object with another Object or Document.

Object-specific EAIP specifications SHALL define valid operations.

---

# 12. State Transitions

EAIP protocols SHALL preserve the state semantics defined by EAIA-0103.

Commands MAY request state transitions.

Events SHOULD record completed state transitions.

State transitions SHALL be validated before completion.

Validation MAY include:

- identity checks
- trust evaluation
- policy evaluation
- capability evaluation
- context evaluation
- mission governance
- safety constraints

---

# 13. Interaction Semantics

EAIP protocols SHALL preserve the interaction semantics defined by EAIA-0104.

Protocol operations SHOULD support the Collaborative Interaction Lifecycle where applicable.

Implementations MAY optimise interaction sequences provided observable behaviour remains interoperable and conformant.

---

# 14. Event Semantics

EAIP protocols SHALL preserve the event semantics defined by EAIA-0105.

Every observable state transition SHOULD produce one or more Events.

Events SHOULD support audit, observability, diagnostics, replay, and interoperability.

Event publication and delivery guarantees are defined by later EAIP specifications.

---

# 15. Identity and Authority

Every Command, Event, Query, and Object representation SHOULD be attributable to an authority.

Authorities MAY include:

- Participants
- Mission owners
- Policy engines
- Trust authorities
- Relay services
- administrative systems

Authority representation is defined by later EAIP identity and addressing specifications.

---

# 16. Correlation

EAIP operations SHOULD support correlation between Commands, Events, Queries, and resulting Objects.

Correlation enables:

- tracing
- audit
- debugging
- distributed workflow reconstruction
- causality analysis

A later EAIP specification SHALL define the common correlation model.

---

# 17. Idempotency

EAIP protocols SHOULD support idempotent operation where practical.

Commands that may be retried SHOULD include sufficient information to detect duplicate execution.

Object-specific protocols SHALL define idempotency requirements.

---

# 18. Errors

EAIP protocols SHALL define explicit error responses for failed operations.

Errors SHOULD distinguish between:

- validation failure
- authorisation failure
- trust failure
- policy rejection
- unavailable capability
- unsuitable context
- timeout
- conflict
- unsupported operation
- malformed request
- internal failure

A later EAIP specification SHALL define the common error model.

---

# 19. Versioning

EAIP specifications SHALL be versioned.

Protocol messages SHOULD identify the protocol version they implement.

Implementations SHOULD support version negotiation where interoperability requires it.

Version negotiation is defined by a later EAIP specification.

---

# 20. Extensibility

EAIP protocols MAY support extensions.

Extensions SHALL NOT alter mandatory semantics defined by the base specification.

Extensions SHALL be clearly identified.

Implementations receiving unknown extensions SHOULD ignore them unless the extension is explicitly marked as mandatory.

---

# 21. Transport Independence

EAIP is transport independent.

EAIP specifications MAY define bindings to specific transports.

Transport bindings SHALL preserve EAIP semantics.

Initial reference implementations MAY use peer-to-peer transport based on iroh.

The architecture SHALL NOT require iroh as the only possible transport.

---

# 22. Security Requirements

EAIP protocols SHALL support security requirements appropriate to their function.

At minimum, security-sensitive operations SHOULD support:

- identity verification
- authentication
- authorisation
- integrity protection
- replay protection
- policy evaluation
- auditability

Security mechanisms are defined by later EAIP specifications.

---

# 23. Privacy Requirements

EAIP protocols SHOULD minimise unnecessary disclosure.

Participants SHOULD retain control over:

- identity disclosure
- capability disclosure
- context disclosure
- event disclosure
- document access

Privacy requirements MAY vary by deployment profile.

---

# 24. Conformance

EAIP conformance SHALL be evaluated according to EAIA-0199.

An EAIP-conformant implementation SHALL:

- preserve EAIA architectural semantics
- implement required protocol behaviour
- preserve object semantics
- preserve event semantics
- preserve state transition semantics
- correctly handle required error conditions

Protocol-specific conformance requirements are defined in each EAIP specification.

---

# 25. Protocol Specification Requirements

Every EAIP protocol specification SHOULD include:

- purpose
- scope
- dependencies
- supported artefact classes
- object model references
- command definitions
- event definitions
- query definitions
- state transition rules
- validation rules
- error conditions
- security considerations
- privacy considerations
- conformance requirements
- examples
- change history

---

# 26. Initial EAIP Roadmap

The initial EAIP foundation is expected to include:

- EAIP-0001 Common Message Envelope
- EAIP-0002 Object Representation
- EAIP-0003 Identity and Addressing
- EAIP-0004 Correlation and Conversation Model
- EAIP-0005 Error Model
- EAIP-0006 Version Negotiation
- EAIP-0007 Event Framework
- EAIP-0008 Discovery Framework
- EAIP-0009 Security Framework

Object-specific protocols are expected to follow.

---

# Security Considerations

This framework establishes common security expectations but does not define cryptographic mechanisms.

Implementations SHALL NOT assume that transport security alone is sufficient for protocol security.

Security-sensitive EAIP operations SHOULD be evaluated against identity, trust, policy, context, and audit requirements.

---

# References

EAIA-0100 — Reference Architecture

EAIA-0102 — Architectural Object Model

EAIA-0103 — Operational State Model

EAIA-0104 — Architectural Interaction Model

EAIA-0105 — Architectural Event Model

EAIA-0199 — Conformance Model

ADR-0001 — Collaboration First

ADR-0003 — Reference Models and Implementation Independence

ADR-0004 — Mission as a First-Class Architectural Object

RFC 2119

RFC 8174

---

# Change History

## 0.1.0

Initial Working Draft.

Established the common framework for the EAIP protocol suite, including Objects, Commands, Events, Queries, and Documents as primary protocol artefact classes.
