# Ntangl

> **The Open Collaboration Standard for Embodied AI**

---

## Overview

Ntangl is an open standards initiative developing the architecture, protocols, reference implementations and governance required for secure collaboration between Embodied AI participants.

The objective is to enable Embodied AI participants from different manufacturers, owners and deployment environments to securely discover one another, establish trust, exchange capabilities and operational context, agree shared goals, allocate work, collaborate safely and complete tasks without proprietary integration.

Ntangl is intended to become the common interoperability layer for Embodied AI in the same way that Internet standards enabled interoperability between heterogeneous computer networks.

---

## Scope

Ntangl defines:

- Reference architecture
- Collaboration model
- Identity architecture
- Trust architecture
- Protocol specifications
- Reference implementations
- Certification framework
- Governance model

Ntangl does **not** define:

- Robot operating systems
- Motion planning
- Computer vision
- Artificial intelligence models
- Hardware design
- Control systems

These remain implementation choices.

---

## Design Philosophy

Ntangl is founded upon several core architectural principles.

- Collaboration First
- Identity Before Interaction
- Trust is Earned
- Context Matters
- Distributed by Default
- Goal-Oriented Collaboration
- Safety Before Optimisation
- Open by Design

These principles are defined within the EAIA architecture documents and are referenced throughout the protocol specifications.

---

## Repository Structure

```text
docs/

    manifesto/
        Vision documents

    architecture/
        Core concepts
        Reference architecture
        Glossary
        Architectural Principles

    adr/
        Architecture Decision Records

    protocols/
        EAIP specifications

    reference-models/
        Example deployments

    governance/
        Standards process

    business/
        Commercial strategy

sdk/

    Reference implementations

schemas/

    Protocol schemas

examples/

    Example deployments

website/

    Documentation site
```

---

## Document Classes

| Prefix | Purpose |
|---------|----------|
| EAIA | Embodied AI Internet Architecture |
| EAIP | Embodied AI Interoperability Protocol |
| ADR | Architecture Decision Record |
| AP | Architectural Principle |
| DG | Design Goal |
| RM | Reference Model |
| CERT | Certification |
| IG | Implementation Guide |

---

## Standards Process

Ntangl adopts an engineering-first documentation process inspired by:

- IETF RFCs
- W3C Recommendations
- Kubernetes Enhancement Proposals
- Architecture Decision Records

Every architectural decision is documented.

Every protocol requirement is traceable back to architectural principles.

---

## Repository Status

Current Release

```
Pre-Alpha
```

Architecture Status

```
Working Draft
```

Protocol Status

```
Draft
```

---

## License

Apache License 2.0

---

## Contributing

Contribution guidelines will be published as the standards process matures.

At present all changes are reviewed through the Architecture Decision process.

---

## Vision

Enable secure collaboration between Embodied AI participants regardless of manufacturer, ownership or deployment environment.

