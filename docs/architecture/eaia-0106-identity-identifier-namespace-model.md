---
document: EAIA-0106
title: Identity, Identifier and Namespace Model
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
  - EAIA-0103
  - EAIA-0199

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

keywords:
  - identity
  - identifier
  - namespace
  - federation

license: Apache-2.0
---

# Status of This Document

This document is a Working Draft.

It defines the architectural concepts of Identity, Identifiers and Namespaces used throughout the Ntangl architecture.

Protocol encodings are defined by the EAIP series.

---

# Abstract

The Ntangl architecture distinguishes between Identity, Identifiers and Namespaces.

Identity represents the enduring semantic existence of an Architectural Object.

Identifiers provide stable references to those objects.

Namespaces provide the administrative and semantic boundaries within which identifiers remain unique.

This separation enables interoperability across federated deployments while allowing different identifier encodings and resolution mechanisms.

---

# 1. Purpose

This document establishes the canonical model for identity and referencing.

It SHALL define:

- Identity
- Identifier
- Namespace
- Ownership
- Resolution
- Federation
- Lifecycle
- Persistence

---

# 2. Scope

This document applies to every first-class Architectural Object.

It intentionally excludes:

- wire encodings
- URI syntax
- UUID formats
- transport addressing
- cryptographic identities

These are specified by the EAIP protocol suite.

---

# 3. Identity

Identity represents the enduring semantic existence of an Architectural Object.

Identity answers:

**"What is this?"**

Identity SHALL be independent of:

- network location
- transport protocol
- implementation language
- deployment topology

Identity MAY outlive any particular implementation.

---

# 4. Identifier

An Identifier is a stable reference to an Architectural Object.

Identifiers answer:

**"How do we refer to this object?"**

Identifiers SHALL:

- uniquely identify an object within an appropriate namespace
- remain stable for the lifetime of the object
- be opaque to implementations
- be suitable for protocol exchange

Applications SHALL NOT infer object semantics from identifier structure.

Identifiers are an architectural mechanism for establishing stable reference rather than an indication of object type. The presence of an identifier does not imply that the identified element is a first-class Architectural Object.

---

# 5. Namespace

A Namespace defines the scope within which identifiers are unique.

Namespaces answer:

**"Within what administrative or semantic boundary is this identifier valid?"**

Namespaces MAY represent:

- organisations
- trust domains
- deployments
- federations
- protocol-defined scopes

Namespaces SHALL support federation.

---

# 6. Architectural Identifier Classes

The architecture defines identifier classes corresponding to first-class Architectural Objects.

Recommended logical prefixes include:

| Object                 | Prefix |
| ---------------------- | ------ |
| Mission                | MIS    |
| Goal                   | GOL    |
| Collaboration          | COL    |
| Collaboration Instance | CLI    |
| Participant            | PAR    |
| Capability             | CAP    |
| Context                | CTX    |
| Trust Relationship     | TRU    |
| Policy                 | POL    |
| Trust Domain           | TDM    |

These prefixes are logical examples only.

Protocol specifications SHALL define their serialized representation.

## Infrastructure Service Identifiers

Architectural Infrastructure Services MAY possess stable identifiers.

Infrastructure Service identifiers are distinct from Architectural Object identifiers.

Service identifier formats are defined by future protocol specifications.

The presence of a Service Identifier SHALL NOT imply that the identified service is an Architectural Object.

---

# 7. Identifier Properties

Identifiers SHOULD be:

- globally unique within their namespace
- stable
- immutable
- opaque
- version-independent

Additional recommended properties include:

* architectural stability across protocol versions

Identifiers SHALL NOT encode mutable operational state.

---

# 8. Architectural Identifiability

The Ntangl architecture recognises that identifiers are not limited to first-class Architectural Objects.

Any architectural element that is intended to be independently referenced, governed, audited, secured, versioned or persisted SHOULD possess a stable identifier.

Examples include, but are not limited to:

* Architectural Objects
* long-lived Collaborations
* Collaboration Instances
* Trust Relationships
* Policies
* architectural Events
* protocol Conversations
* delegated authorities
* externally referenced Documents

The decision to assign an identifier SHALL be based on the architectural role of the element rather than its implementation.

Architectural elements that are transient, implementation-specific or not intended for independent reference SHOULD NOT require stable identifiers.

Future EAIA and EAIP specifications MAY define additional identifiable architectural elements provided they preserve the identity, identifier and namespace semantics established by this document.

---

# 9. Ownership

Every Architectural Object SHALL have an authoritative owner.

Ownership and identity are distinct concepts.

Ownership MAY change.

Identity SHALL remain constant.

---

# 10. Resolution

Identifier resolution is the process of obtaining information about an Architectural Object.

Resolution MAY return:

- object representations
- object metadata
- current state
- historical information
- policy-controlled subsets

Resolution mechanisms are protocol-specific.

---

# 11. Federation

Ntangl assumes a federated architecture.

Identifiers SHALL support interoperability across multiple administrative domains.

Federation SHALL NOT require a single global authority.

Implementations MAY employ distributed resolution mechanisms.

---

# 12. Lifecycle

Identifiers are created when an Architectural Object is created.

Identifiers remain associated with the object throughout its lifecycle.

Identifiers SHOULD NOT be reused after object retirement.

Archived objects SHALL retain their identifiers.

---

# 13. Privacy

Identifiers SHOULD minimise unnecessary disclosure.

Public identifiers and private identifiers MAY coexist.

Resolution services MAY return different information depending on policy and trust.

---

# 14. Security Considerations

Identifiers SHALL support:

- integrity
- authenticity
- resistance to spoofing

Identifier validation mechanisms are protocol-specific.

The architecture does not mandate a specific cryptographic identity scheme.

---

# 15. Relationship to EAIP

The EAIA series defines:

- identity semantics
- identifier semantics
- namespace semantics

The EAIP series defines:

- identifier encoding
- identifier transport
- resolution protocols
- discovery mechanisms

---

# References

EAIA-0100 — Reference Architecture

EAIA-0102 — Architectural Object Model

EAIA-0103 — Operational State Model

EAIA-0199 — Conformance Model

RFC 2119

RFC 8174

---

# Change History

## 0.1.0

Initial Working Draft.

Established the canonical Identity, Identifier and Namespace Model for the Ntangl architecture.
