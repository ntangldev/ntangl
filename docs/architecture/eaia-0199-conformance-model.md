---
document: EAIA-0199
title: Ntangl Conformance Model
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
  - EAIA-0105

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
  - Architects
  - Implementers
  - SDK Developers
  - Certification Bodies
  - Manufacturers

keywords:
  - conformance
  - certification
  - interoperability
  - compliance

license: Apache-2.0
---

# Status of This Document

This document is a Working Draft.

It defines the architectural conformance model for Ntangl.

Protocol-specific conformance requirements are defined by the EAIP series.

---

# Abstract

The Ntangl Conformance Model defines the levels of conformance applicable to implementations of the Ntangl architecture.

Conformance is evaluated independently at the architectural, protocol and profile levels.

This separation allows implementations to interoperate while supporting different deployment environments, capabilities and application domains.

---

# 1. Purpose

This document establishes a common conformance framework for the Ntangl standards.

The Conformance Model SHALL:

- define conformance categories
- define implementation obligations
- separate architecture from protocol conformance
- support partial implementations
- support certification
- preserve interoperability

---

# 2. Scope

This document applies to:

- software implementations
- SDKs
- runtime platforms
- embodied intelligence systems
- relay services
- protocol gateways
- simulation environments
- testing frameworks

---

# 3. Conformance Philosophy

Ntangl defines interoperability through observable behaviour.

Conformance SHALL be evaluated according to:

- architectural semantics
- protocol behaviour
- profile requirements

Conformance SHALL NOT depend upon:

- programming language
- operating system
- hardware architecture
- deployment model
- implementation technique

---

# 4. Conformance Layers

The Ntangl Conformance Model consists of four layers.

```text
Architecture

↓

Protocols

↓

Profiles

↓

Certification
```

Each layer builds upon the previous layer.

---

# 5. Architecture Conformance

Architecture Conformance demonstrates that an implementation correctly models the architectural concepts defined by the EAIA series.

An Architecture Conformant implementation SHALL:

- implement the architectural object model
- preserve architectural semantics
- implement valid state transitions
- preserve interaction semantics
- preserve event semantics

Architecture Conformance does not require implementation of any specific protocol.

---

# 6. Protocol Conformance

Protocol Conformance demonstrates compliance with one or more EAIP protocol specifications.

Each implemented protocol SHALL satisfy all mandatory requirements defined within the corresponding EAIP specification.

Protocol Conformance is evaluated independently for each protocol.

Examples include:

- Participant Protocol
- Mission Protocol
- Goal Protocol
- Trust Protocol
- Collaboration Protocol

---

# 7. Profile Conformance

Profiles define interoperable subsets of the Ntangl standards for specific deployment domains.

Example profiles include:

- Warehouse Automation
- Healthcare
- Construction
- Agriculture
- Space Operations
- Consumer Robotics

A Profile SHALL specify:

- mandatory protocols
- optional protocols
- required object support
- minimum capabilities
- interoperability expectations

---

# 8. Certification

Certification provides independent verification of conformance.

Certification MAY evaluate:

- architecture
- protocols
- profiles
- interoperability
- security
- performance

Certification procedures are defined separately.

---

# 9. Conformance Classes

An implementation MAY claim one or more conformance classes.

## Architecture Conformant

Implements the EAIA architecture.

---

## Protocol Conformant

Implements one or more EAIP protocols.

---

## Profile Conformant

Implements a published Ntangl Profile.

---

## Certified

Has successfully completed an approved certification programme.

---

# 10. Observable Behaviour

Conformance SHALL be evaluated through observable behaviour.

Observable behaviour includes:

- object semantics
- protocol exchanges
- state transitions
- architectural events
- interoperability

Internal implementation SHALL NOT form part of conformance evaluation.

---

# 11. Extensibility

Implementations MAY introduce proprietary extensions.

Extensions SHALL:

- preserve interoperability
- preserve architectural semantics
- avoid modifying normative behaviour

Extensions SHALL be clearly identified.

---

# 12. Version Compatibility

Implementations SHOULD declare:

- supported architecture version
- supported protocol versions
- supported profiles

Version negotiation is protocol-specific.

---

# 13. Conformance Claims

Implementations SHOULD express conformance using the following format.

Examples:

```
EAIA 1.0 Architecture Conformant

EAIP-0100 Participant Protocol Conformant

EAIP-0200 Mission Protocol Conformant

Warehouse Profile Conformant

Ntangl Certified
```

Multiple claims MAY be combined.

---

# 14. Relationship to EAIP

The EAIA series defines:

- architectural semantics
- conformance model

The EAIP series defines:

- protocol requirements
- protocol conformance tests
- interoperability requirements

Certification SHALL evaluate protocol behaviour against both EAIA and EAIP requirements.

---

# Security Considerations

Security-sensitive deployments SHOULD require protocol and profile conformance in addition to architecture conformance.

Architecture Conformance alone does not imply secure implementation.

---

# References

EAIA-0100 — Reference Architecture

EAIA-0102 — Architectural Object Model

EAIA-0103 — Operational State Model

EAIA-0104 — Architectural Interaction Model

EAIA-0105 — Architectural Event Model

RFC 2119

RFC 8174

---

# Change History

## 0.1.0

Initial Working Draft.

Established the Ntangl Conformance Model.
