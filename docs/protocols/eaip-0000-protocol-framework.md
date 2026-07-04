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

EAIP protocols define interoperable representations and operations for the Architectural Objects defined by the EAIA series.

The protocol framework recognises six primary protocol artefact classes:

* Object
* Command
* Response
* Event
* Query
* Document

These artefact classes provide a consistent semantic model for all EAIP protocol specifications.

---

# 1. Purpose

The purpose of this document is to define the common foundation for all EAIP protocol specifications.

EAIP-0000 SHALL establish:

* the relationship between EAIA and EAIP
* the common protocol artefact classes
* the common protocol operation model
* the distinction between Objects, Commands, Responses, Events, Queries and Documents
* shared conformance expectations
* baseline protocol design constraints

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

EAIP defines interoperable protocol behaviour for:

* Architectural Objects
* Architectural Infrastructure Services

Protocol operations affecting Architectural Objects SHALL preserve EAIA semantics.

Protocol operations interacting with Architectural Infrastructure Services SHALL preserve service semantics without altering the architectural meaning of the underlying Objects.

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

| Artefact | Purpose                                                   |
| -------- | --------------------------------------------------------- |
| Object   | Persistent architectural entity                           |
| Command  | Request to perform an action or cause a state transition  |
| Response | Immediate outcome of processing a Command or Query        |
| Event    | Immutable fact recording something that occurred          |
| Query    | Request for information without requesting a state change |
| Document | External supporting artefact referenced by the protocol   |

These artefact classes SHALL be used consistently throughout the EAIP protocol suite.

Architectural Infrastructure Services are not protocol artefacts.

They provide infrastructure capabilities supporting the exchange, discovery, validation and distribution of protocol artefacts.

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

# 8. Response

A Response communicates the outcome of processing a Command or Query.

Responses describe the result of protocol processing.

Responses SHALL NOT be interpreted as evidence that an architectural state transition has occurred.

Typical Response outcomes include:

* Accepted
* Rejected
* Completed
* Deferred
* Unsupported
* Invalid
* Not Authorised
* Conflict
* Timeout
* Error

A Response SHOULD identify:

* response identifier
* related Command or Query
* processing outcome
* responding authority
* timestamp
* correlation identifier
* optional diagnostic information

Responses MAY be followed by one or more Events if processing results in observable architectural state transitions.

---

# 9. # Event

An Event records an immutable architectural fact.

Events are produced as the consequence of successful or otherwise observable state transitions.

Events SHALL NOT be generated solely because a Command or Query was received.

Events represent completed facts rather than processing outcomes.

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

# 10. Query

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

# 11. Document

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

# 12. Operation Model

EAIP protocols generally operate by exchanging Commands, Responses, Queries and Events while creating, reading, updating, referencing and observing Architectural Objects.

Documents provide supporting information but are not themselves governed by the Architectural Object Model.

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

# 13. State Transitions

Commands MAY request state transitions.

Responses communicate whether processing of the request was accepted, rejected, deferred or otherwise completed.

Events SHOULD record successful or otherwise observable state transitions.

Not every accepted Command results in an immediate Event.

Not every Response results in an Event.

Protocol specifications SHALL define the relationship between Commands, Responses and Events for each operation.

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

# 14. Interaction Semantics

EAIP protocols SHALL preserve the interaction semantics defined by EAIA-0104.

Protocol operations SHOULD support the Collaborative Interaction Lifecycle where applicable.

Implementations MAY optimise interaction sequences provided observable behaviour remains interoperable and conformant.

---

# 15. Event Semantics

EAIP protocols SHALL preserve the event semantics defined by EAIA-0105.

Every observable state transition SHOULD produce one or more Events.

Events SHOULD support audit, observability, diagnostics, replay, and interoperability.

Event publication and delivery guarantees are defined by later EAIP specifications.

---

# 16. Identity and Authority

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

# 17. Correlation

EAIP operations SHOULD support correlation between Commands, Responses, Events, Queries and the resulting Architectural Objects.

Correlation enables complete reconstruction of distributed interactions from request through completion.

Correlation enables:

- tracing
- audit
- debugging
- distributed workflow reconstruction
- causality analysis

A later EAIP specification SHALL define the common correlation model.

---

# 18. Idempotency

EAIP protocols SHOULD support idempotent operation where practical.

Commands that may be retried SHOULD include sufficient information to detect duplicate execution.

Object-specific protocols SHALL define idempotency requirements.

---

# 19. Error Handling

Malformed Commands, Queries and other protocol artefacts SHALL result in appropriate Responses.

Errors SHALL be represented using the Response model.

Errors SHALL NOT be represented as Events unless an architectural state transition has occurred.

The common Response and Error Model is defined by EAIP-0005.

---

# 20. Versioning

EAIP specifications SHALL be versioned.

Protocol messages SHOULD identify the protocol version they implement.

Implementations SHOULD support version negotiation where interoperability requires it.

Version negotiation is defined by a later EAIP specification.

---

# 21. Extensibility

EAIP protocols MAY support extensions.

Extensions SHALL NOT alter mandatory semantics defined by the base specification.

Extensions SHALL be clearly identified.

Implementations receiving unknown extensions SHOULD ignore them unless the extension is explicitly marked as mandatory.

---

# 22. Transport Independence

EAIP is transport independent.

EAIP specifications MAY define bindings to specific transports.

Transport bindings SHALL preserve EAIP semantics.

Initial reference implementations MAY use peer-to-peer transport based on iroh.

The architecture SHALL NOT require iroh as the only possible transport.

---

# 23. Security Requirements

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

# 24. Privacy Requirements

EAIP protocols SHOULD minimise unnecessary disclosure.

Participants SHOULD retain control over:

- identity disclosure
- capability disclosure
- context disclosure
- event disclosure
- document access

Privacy requirements MAY vary by deployment profile.

---

# 25. Conformance

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

# 26. Protocol Specification Requirements

Every EAIP protocol specification SHOULD include:

* purpose
* scope
* supported Architectural Objects
* supported Commands
* supported Responses
* supported Events
* supported Queries
* supported Document references
* state transition rules
* validation rules
* security considerations
* privacy considerations
* conformance requirements
* examples
* change history

---

# 27. Initial EAIP Roadmap

The initial EAIP foundation is expected to include:

* EAIP-0001 Common Message Model
* EAIP-0002 Object Representation Model
* EAIP-0003 Identity and Addressing
* EAIP-0004 Correlation and Conversation Model
* EAIP-0005 Response and Error Model
* EAIP-0006 Version Negotiation
* EAIP-0007 Event Framework
* EAIP-0008 Discovery Framework
* EAIP-0009 Security Framework

Object-specific protocols are expected to build upon these common specifications.

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
