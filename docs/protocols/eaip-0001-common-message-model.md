---
document: EAIP-0001
title: Common Message Model
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
  - EAIP-0000

related:
  - EAIA-0102
  - EAIA-0103
  - EAIA-0104
  - EAIA-0105

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

audience:
  - Protocol Designers
  - SDK Developers
  - Implementers

keywords:
  - message
  - envelope
  - protocol

license: Apache-2.0
---

# Status of This Document

This document is a Working Draft.

It defines the canonical message model used throughout the EAIP protocol suite.

All EAIP protocol specifications SHALL conform to this model unless explicitly stated otherwise.

---

# Abstract

The Common Message Model establishes the common semantic structure shared by every EAIP protocol message.

It defines message composition independently of serialization format, transport protocol or programming language.

Protocol-specific message schemas extend this model while preserving interoperability.

---

# 1. Purpose

The Common Message Model SHALL provide:

- a common message structure
- consistent routing semantics
- correlation support
- extensibility
- transport independence
- security integration

---

# 2. Scope

This specification defines:

- message composition
- message semantics
- mandatory message sections
- artefact embedding
- attachment model
- extension model

It intentionally does not define:

- serialization
- wire encoding
- transport bindings
- cryptographic algorithms

---

# 3. Message Structure

Every EAIP message SHALL consist of the following logical sections.

```text
Message
│
├── Envelope
├── Routing
├── Security
├── Body
├── Attachments
└── Extensions
```

The physical encoding MAY differ.

The logical semantics SHALL remain consistent.

---

# 4. Envelope

The Envelope identifies the message.

Every Envelope SHOULD contain:

- protocol version
- specification identifier
- message identifier
- message type
- creation timestamp

The Envelope SHALL remain immutable after message creation.

---

# 5. Routing

Routing identifies communication endpoints.

Routing information MAY include:

- sender
- recipient
- relay path
- conversation identifier
- response destination
- delivery policy

Routing SHALL remain independent of transport technology.

---

# 6. Security

The Security section identifies the authority responsible for the message.

Typical information includes:

- originating authority
- authentication information
- integrity information
- authorisation context
- trust references
- policy references

Cryptographic mechanisms are defined separately.

---

# 7. Body

The Body SHALL contain one primary protocol artefact.

Supported artefacts include:

- Object
- Command
- Response
- Event
- Query

A Body SHALL NOT contain multiple primary artefacts.

Relationships between artefacts SHALL be represented through identifiers rather than nesting unrelated operations.

---

# 8. Attachments

Attachments reference supporting artefacts.

Examples include:

- procedures
- CAD models
- maps
- images
- certificates
- inspection reports
- datasets

Attachments MAY be embedded or externally referenced.

Attachment transport is implementation specific.

---

# 9. Extensions

Extensions provide forward compatibility.

Extensions SHALL:

- be optional unless explicitly required
- preserve base semantics
- avoid modifying normative behaviour

Unknown extensions SHOULD be ignored unless declared mandatory.

---

# 10. Message Lifecycle

Typical lifecycle:

```text
Created

↓

Validated

↓

Authorised

↓

Transmitted

↓

Received

↓

Processed

↓

Archived
```

Implementations MAY introduce additional internal states.

---

# 11. Correlation

Messages SHOULD support correlation.

Correlation enables:

- request/response matching
- event tracing
- workflow reconstruction
- distributed debugging

Correlation identifiers SHALL remain stable throughout a conversation.

---

# 12. Conversations

Messages MAY participate in conversations.

A conversation represents a logical sequence of related messages.

Conversations MAY include:

- Commands
- Responses
- Events
- Queries

Conversation semantics are defined by EAIP-0004.

---

# 13. Idempotency

Commands intended for retry SHOULD include idempotency identifiers.

Receivers SHOULD detect duplicate execution where required.

Idempotency requirements are protocol-specific.

---

# 14. Transport Independence

The Common Message Model is transport independent.

Messages MAY be exchanged using:

- iroh
- QUIC
- HTTP
- DDS
- MQTT
- future transports

Transport bindings SHALL preserve message semantics.

---

# 15. Error Handling

Malformed messages SHALL be rejected.

Validation failures SHALL produce appropriate Responses where possible.

Error representation is defined by EAIP-0005.

---

# 16. Security Considerations

Sensitive message sections SHOULD be protected according to protocol requirements.

Implementations SHOULD support:

- integrity
- authenticity
- confidentiality where required
- replay protection
- auditability

---

# 17. Extensibility

Future message sections MAY be introduced.

New sections SHALL preserve backward compatibility wherever practical.

Extensions SHALL NOT redefine existing semantics.

---

# 18. Conformance

An implementation claiming conformance to this specification SHALL:

- implement the logical message structure
- preserve artefact semantics
- support required Envelope fields
- correctly process supported artefact classes
- preserve correlation identifiers
- preserve message immutability where required

Serialization format is not part of conformance.

---

# References

EAIP-0000 — Protocol Framework

EAIA-0102 — Architectural Object Model

EAIA-0103 — Operational State Model

EAIA-0104 — Architectural Interaction Model

EAIA-0105 — Architectural Event Model

EAIA-0199 — Conformance Model

RFC 2119

RFC 8174

---

# Change History

## 0.1.0

Initial Working Draft.

Established the common message model for the EAIP protocol suite.
