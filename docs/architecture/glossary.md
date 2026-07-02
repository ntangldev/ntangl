---
document: EAIA-0001
title: Glossary
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
  - ADR-0001
  - ADR-0002

related:
  - EAIA-0000

architectural_principles:
  - AP-0001

design_goals:
  - DG-0001

audience:
  - Architects
  - Implementers

keywords:
  - terminology
  - glossary

license: Apache-2.0
---

# Status of This Document

This document is a Working Draft.

Definitions contained within this document SHALL be considered authoritative unless superseded by a later version.

---

# Purpose

This glossary establishes the canonical terminology used throughout the Ntangl Standards Repository.

---

# Embodied AI

Software-defined intelligence embodied within one or more physical systems capable of interacting with the physical world.

---

# Embodied AI Participant

A uniquely identifiable network participant that possesses:

- a persistent identity
- declared capabilities
- operational context

and is capable of participating in collaborative activities.

---

# Sovereign Participant

A participant that maintains authority over its own identity, local state and interaction decisions while operating within the governance policies imposed by its owner, operator and deployment environment.

Sovereignty is an architectural property and does not imply legal personhood, consciousness or moral agency.

---

# Capability

A declared ability that a participant MAY perform under suitable operating conditions.

Capabilities MAY be static or dynamic.

---

# Context

Operational information describing the participant's current ability to contribute to a collaboration.

Context MAY include:

- location
- battery state
- task allocation
- safety state
- environmental conditions
- available tools
- communication status

---

# Goal

A shared operational outcome that one or more participants seek to achieve.

Goals SHALL define the desired result rather than the implementation.

---

# Collaboration

A coordinated activity involving two or more participants working towards one or more shared goals.

---

# Collaborative Interaction Lifecycle (CIL)

The canonical operational model describing the activities required to establish, execute and complete collaboration between participants.

The reference lifecycle is:

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

The lifecycle defines a conceptual sequence rather than a mandatory protocol exchange.

Implementations MAY optimise, combine or reorder individual activities where interoperability, security and safety are preserved.

---

# Trust Domain

A set of participants operating under a common trust policy.

Trust domains MAY overlap.

---

# Relay

A network service that assists participants with discovery and communication where direct peer-to-peer connectivity is unavailable.

Relays SHALL NOT become authoritative decision makers within collaborations.

---

# Change History

## 0.1.0

Initial Working Draft.
