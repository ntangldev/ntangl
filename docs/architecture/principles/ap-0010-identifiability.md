---
document: AP-0010
title: Identifiability
status: Working Draft
maturity: Foundation
version: 0.1.0

category: Architectural Principle

editors:
  - Devinda Poodoo
  - OpenAI (Technical Editor)

created: 2026-07-01
updated: 2026-07-01

depends_on:
  - EAIA-0102
  - EAIA-0106

related:
  - ADR-0004

architectural_principles:
  - AP-0001
  - AP-0003
  - AP-0005
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
  - Standards Bodies

keywords:
  - identity
  - identifier
  - namespace
  - architecture

license: Apache-2.0
---

# Status of This Document

This document is a Working Draft.

Architectural Principles define enduring design guidance for the Ntangl architecture and are expected to remain stable across protocol generations.

---

# Principle

Architectural elements that require independent reference, governance, audit, security, persistence or versioning SHOULD possess stable identifiers.

The decision to assign an identifier SHALL be driven by architectural semantics rather than implementation details.

---

# Rationale

Identifiers are fundamental to interoperability in distributed systems.

Stable identifiers enable Participants to reference architectural elements consistently across protocols, implementations, administrative domains and time.

Identifiers support:

- interoperability
- auditability
- governance
- traceability
- persistence
- federation
- version-independent reference

The presence of an identifier does not imply that an element is a first-class Architectural Object.

Likewise, not every implementation artefact requires a stable identifier.

---

# Guidance

Architects SHOULD evaluate new concepts using the following questions.

## Responsibility

Does the element have a distinct architectural responsibility?

If not, it SHOULD remain part of another architectural element.

---

## Independent Reference

Will other architectural elements need to reference it independently?

If yes, it SHOULD possess a stable identifier.

---

## Lifecycle

Does the element possess an independent lifecycle?

Elements with independent lifecycles SHOULD generally possess independent identifiers.

---

## Governance

Is the element independently governed?

If governance decisions can be applied independently, the element SHOULD possess its own identifier.

---

## Audit

Will the element appear in audit records?

If yes, a stable identifier SHOULD be used.

---

## Persistence

Will the element outlive an individual protocol exchange?

Persistent architectural elements SHOULD possess stable identifiers.

---

# Examples

Examples of identifiable architectural elements include:

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
- Architectural Event
- Protocol Conversation
- Delegated Authority
- Referenced Document

Examples of implementation artefacts that do not normally require architectural identifiers include:

- temporary buffers
- transport sessions
- local caches
- implementation threads
- protocol parser state
- transient message fragments

---

# Architectural Consequences

Applying this principle results in:

- improved interoperability
- consistent auditability
- protocol independence
- implementation flexibility
- simplified federation

Architectural identifiers become long-lived semantic references rather than implementation artefacts.

---

# Relationship to Other Principles

This principle complements:

**AP-0001 — Architecture Before Implementation**

Identifiers are architectural concepts and SHALL NOT be constrained by implementation technology.

**AP-0003 — Protocol Independence**

Identifier semantics SHALL remain independent of protocol representation.

**AP-0005 — Persistent Identity**

Stable identifiers enable persistent identity across protocol exchanges and deployments.

**AP-0009 — Operational Separation of Concerns**

Independent architectural responsibilities frequently imply the need for independent identifiers.

---

# Implementation Notes (Informative)

Implementations are free to represent identifiers using any suitable encoding, including UUIDs, URNs, hashes, hierarchical names or future schemes.

Identifier encoding is specified by the EAIP protocol series and is intentionally outside the scope of this principle.

---

# References

EAIA-0102 — Architectural Object Model

EAIA-0106 — Identity, Identifier and Namespace Model

ADR-0004 — Mission as a First-Class Architectural Object

RFC 2119

RFC 8174

---

# Change History

## 0.1.0

Initial Working Draft.

Established Identifiability as a core architectural principle governing the assignment of stable identifiers to architectural elements.
