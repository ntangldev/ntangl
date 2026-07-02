---
document: ADR-0003
title: Reference Models and Implementation Independence
status: Accepted
maturity: Foundation
version: 1.0.0

category: Architecture Decision

editors:
  - Devinda Poodoo
  - OpenAI (Technical Editor)

created: 2026-07-01
updated: 2026-07-01

depends_on:
  - ADR-0001
  - ADR-0002

related:
  - EAIA-0000
  - EAIA-0001
  - EAIA-0002

architectural_principles:
  - AP-0001
  - AP-0004
  - AP-0008

design_goals:
  - DG-0001
  - DG-0003
  - DG-0006
  - DG-0007

audience:
  - Architects
  - Protocol Designers
  - Implementers
  - Certification Authorities

keywords:
  - reference architecture
  - interoperability
  - implementation
  - conformance

license: Apache-2.0
---

# Status of This Document

This Architecture Decision has been **Accepted**.

Architecture Decisions are normative within the Ntangl Standards Repository.

---

# Abstract

This document establishes the relationship between the conceptual models defined by the Ntangl architecture and the behaviour required of conforming implementations.

Ntangl specifies interoperable behaviour rather than implementation techniques.

Reference models define the architectural intent of the standards. Implementations remain free to optimise, combine or extend internal behaviour provided interoperability, security and safety requirements are preserved.

---

# Context

Distributed systems evolve over long periods of time and across many organisations.

Implementations inevitably differ due to:

- hardware capabilities
- operating environments
- performance requirements
- programming languages
- deployment constraints
- commercial considerations

If the standards prescribe implementation details rather than externally observable behaviour, they unnecessarily constrain innovation while providing little additional interoperability.

Successful Internet standards define what compliant systems MUST do while intentionally avoiding unnecessary constraints on how they achieve those outcomes.

Ntangl adopts the same philosophy.

---

# Decision

The Ntangl Standards Repository SHALL distinguish between:

- architectural models
- protocol specifications
- implementation guidance
- reference implementations

These represent different layers of abstraction.

Architectural models SHALL describe concepts, relationships and operational behaviour.

Protocol specifications SHALL define normative interoperability requirements.

Reference implementations SHALL demonstrate one possible implementation of the standards.

Implementation Guides MAY recommend implementation approaches but SHALL NOT redefine normative protocol behaviour.

---

# Reference Models

Reference models exist to explain the architecture.

They SHALL NOT be interpreted as mandatory implementation designs.

Reference models MAY describe:

- conceptual lifecycles
- logical components
- interaction patterns
- information flows
- trust relationships

Reference models SHOULD remain stable over time.

---

# Operational Models

Operational models describe the canonical behaviour of the architecture.

For example, the Collaborative Interaction Lifecycle defines the conceptual stages of collaboration.

Operational models SHALL be treated as architectural reference models.

They SHALL NOT be interpreted as mandatory protocol message sequences unless explicitly stated by a normative specification.

---

# Implementation Independence

Conforming implementations MAY:

- combine lifecycle stages
- optimise internal processing
- cache information
- parallelise operations
- introduce implementation-specific optimisations
- employ proprietary internal algorithms

provided that:

- observable behaviour remains compliant
- interoperability is preserved
- security guarantees are maintained
- safety requirements continue to be satisfied

---

# Protocol Conformance

Protocol conformance SHALL be determined by externally observable behaviour rather than internal implementation.

Conformance testing SHOULD verify:

- protocol correctness
- interoperability
- security behaviour
- safety behaviour

Conformance SHALL NOT require identical internal software architecture.

---

# Rationale

This approach provides several important benefits.

## Innovation

Implementers remain free to improve performance and efficiency without requiring changes to the standards.

## Longevity

Architectural concepts remain stable even as implementation technology evolves.

## Interoperability

Independent implementations can collaborate provided they satisfy the protocol specifications.

## Vendor Neutrality

The standards avoid favouring any particular implementation strategy, programming language or deployment architecture.

---

# Consequences

Future EAIA documents SHALL distinguish clearly between conceptual architecture and normative protocol requirements.

Future EAIP specifications SHALL define externally observable behaviour rather than implementation techniques.

Certification SHALL evaluate conformance against protocol behaviour rather than implementation structure.

Reference implementations SHALL remain informative rather than normative.

---

# Examples

## Example 1

The Collaborative Interaction Lifecycle describes the canonical sequence:

1. Discover
2. Identify
3. Establish Trust
4. Exchange Capabilities
5. Exchange Context
6. Agree Goal
7. Allocate Tasks
8. Execute
9. Monitor
10. Complete

An implementation MAY combine identity verification and trust evaluation into a single protocol exchange provided equivalent security guarantees are maintained.

---

## Example 2

A participant MAY cache trust assertions from previous interactions.

Provided the assertions remain valid under local policy and protocol requirements, the participant is not required to repeat the complete trust establishment procedure for every interaction.

---

## Example 3

A participant MAY evaluate capabilities and operational context concurrently rather than sequentially.

Provided both are considered before collaboration commitments are established, the implementation remains conformant.

---

# References

ADR-0001 — Collaboration First

ADR-0002 — Documentation Standards

EAIA-0000 — The Embodied AI Internet Manifesto

EAIA-0001 — Glossary

EAIA-0002 — Collaborative Interaction Lifecycle

RFC 2119 — Key words for use in RFCs to Indicate Requirement Levels

RFC 8174 — Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words

---

# Change History

## 1.0.0

Initial Accepted Architecture Decision.

Established the distinction between architectural models, protocol specifications and implementation behaviour.
