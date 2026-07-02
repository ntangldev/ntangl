---
document: EAIA-0000
title: The Embodied AI Internet Manifesto
status: Working Draft
maturity: Foundation
version: 0.1.0

category: Manifesto

editors:
  - Devinda Poodoo
  - OpenAI (Technical Editor)

created: 2026-07-01
updated: 2026-07-01

depends_on:
  - ADR-0001
  - ADR-0002

related:
  - EAIA-0001

architectural_principles:
  - AP-0001

design_goals:
  - DG-0001

audience:
  - Architects
  - Researchers
  - Standards Bodies
  - Industry

keywords:
  - embodied-ai
  - interoperability
  - collaboration

license: Apache-2.0
---

# Status of This Document

This document is a Working Draft.

It defines the vision and guiding philosophy of the Ntangl initiative.

Unlike protocol specifications, this document is informative rather than normative.

---

# Abstract

Embodied AI systems are becoming increasingly capable and are beginning to operate across organisational, geographic and operational boundaries.

While individual systems continue to advance rapidly, collaboration between systems from different manufacturers remains fragmented by proprietary interfaces and closed ecosystems.

Ntangl proposes a common collaboration architecture that enables participants to securely discover one another, establish trust, exchange capabilities and operational context, agree shared goals and collaborate safely without proprietary integration.

---

# The Problem

Today's embodied AI deployments are largely isolated.

Although many systems communicate effectively within proprietary ecosystems, collaboration across vendors, operators and deployment environments remains difficult and expensive.

As a consequence:

- integration costs remain high
- deployments remain fragmented
- vendor lock-in persists
- innovation is constrained by closed interfaces

The physical world lacks an open collaboration layer comparable to the role that Internet standards play in the exchange of information.

---

# Vision

Enable any Participant implementing the Ntangl architecture to securely collaborate with any other Participant regardless of manufacturer, ownership or deployment environmen

---

# Guiding Principles

Ntangl is founded upon several architectural principles.

These principles are expanded in dedicated architecture documents and applied consistently throughout the protocol specifications.

The architectural principles define enduring characteristics of the Ntangl architecture.

Operational models, including the Collaborative Interaction Lifecycle, provide canonical guidance for protocol design but do not prescribe specific implementation strategies unless explicitly stated by a normative specification.

The initial principles are:

- Collaboration First
- Identity Before Interaction
- Trust is Earned
- Distributed by Default
- Context Matters
- Goal-Oriented Collaboration
- Safety Before Optimisation
- Open by Design

---

# Scope

Ntangl defines the architecture required to enable secure collaboration between participants.

Ntangl does not define:

- robot operating systems
- perception systems
- motion planning
- AI models
- hardware platforms
- fleet management products

These remain implementation choices.

---

# Long-Term Vision

The long-term objective of Ntangl is to establish an open, vendor-neutral collaboration standard for Embodied AI.

By providing common mechanisms for identity, trust, capability exchange, context sharing and collaboration, Ntangl seeks to reduce integration effort, encourage interoperability and enable new classes of collaborative applications.

---

# Future Work

The Ntangl Standards Repository will progressively define:

- architectural principles
- reference architecture
- protocol specifications
- reference implementations
- certification framework
- governance model

---

# Change History

## 0.1.0

Initial Working Draft.
