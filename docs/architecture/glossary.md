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

# Foundational Concepts

---

# Participant

The logical network identity recognised by Ntangl.

A Participant represents the entity that
discovers,
establishes trust,
declares capabilities,
shares context,
accepts commitments,
and participates in collaboration.

A Participant may represent:

• one embodied intelligence
• multiple coordinated embodiments
• a fleet
• infrastructure
• future implementation models

---

# Embodied AI

Historical industry term.

Within Ntangl, Embodied Intelligence
is the preferred architectural term.

---

# Embodied Intelligence

---
# Embodiment

---

# Goal

A measurable operational outcome contributing to the completion of a mission

Goals define what must be acheived but do not define why the work exists.

One Mission may contain multiple goals

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

# Trust Domain

A set of participants operating under a common trust policy.

Trust domains MAY overlap.

---

# Relay

A network service that assists participants with discovery and communication where direct peer-to-peer connectivity is unavailable.

Relays SHALL NOT become authoritative decision makers within collaborations.

---

# Collaboration

A coordinated activity performed by Participants to achieve one or more goals

---

# Collaboration Instance

A specific execution of a Collaboration associated with one or more Goals within a Mission.

---

# Mission

An authorised unit of work initiated by a requestor that defines operational intent and governance for one or more goals

A Mission specifies:

   "requesting authority"
   "objectives"
   "constraints"
   "priorities"
   "policies"
   "success criteria"

A Mission may contain one or more goals

---

# Lifecycle

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

# Protocol Concepts

---

# Change History

## 0.1.0

Initial Working Draft.
