# Title

Status:
Draft

---

## Architectural Question

TODO

---

## Background

TODO

---

## Alternatives Explored

TODO

---

## Discussion

TODO

---

## Key Insights

TODO

---

## Decision

TODO

---

## Consequences

TODO

---

## Remaining Questions

TODO

---

## Related Documents

TODO
# Domain Before Technology

**Status:** Accepted

---

## Architectural Question

Should the architecture of the Engineering Intelligence Platform be driven by technology choices or by the business domain it seeks to model?

The objective of this discussion was to establish the order in which engineering decisions should be made throughout the lifetime of the project.

---

## Background

Software projects frequently begin by selecting technologies.

Common examples include:

- Spring Boot
- PostgreSQL
- Neo4j
- Kafka
- Kubernetes
- React

Although these technologies are important, they describe *how* a system is implemented rather than *what* the system fundamentally represents.

Early discussions around this project also naturally drifted toward infrastructure, databases and AI frameworks.

However, those discussions repeatedly exposed an important problem.

Without first understanding the business domain, every technical decision became speculative.

---

## Alternatives Explored

### Technology-First Development

Begin by selecting frameworks, infrastructure and implementation patterns.

The domain model evolves around those technical choices.

#### Advantages

- Faster initial development.
- Familiar workflow for many teams.
- Early technical validation.

#### Limitations

- Business concepts become constrained by implementation.
- Domain terminology often mirrors framework terminology.
- Architectural decisions become difficult to reverse.
- Long-term maintainability suffers.

---

### Domain-First Development

Begin by understanding the business domain, identifying core concepts and defining relationships independently of technology.

Technology is introduced only after the domain model is sufficiently understood.

#### Advantages

- Business concepts remain stable.
- Implementation becomes a translation of the domain.
- Frameworks become replaceable.
- Architecture reflects business requirements rather than technical convenience.

#### Limitations

- Requires greater upfront exploration.
- Delays implementation.
- Demphasises rapid prototyping in favour of long-term clarity.

---

## Discussion

Throughout the architecture discovery process, a recurring pattern emerged.

Questions initially framed around technology consistently transformed into questions about the business domain.

For example:

Instead of asking:

*"Should we use Neo4j?"*

The discussion became:

*"What business artifact are we trying to represent?"*

Instead of asking:

*"Should Workspace own repositories?"*

The discussion became:

*"What responsibilities belong to a Workspace?"*

Rather than selecting technologies first, the project gradually shifted toward identifying stable business concepts.

Only after those concepts became clear did implementation choices begin to make sense.

---

## Key Insights

### The domain is the source of truth.

Frameworks, databases and infrastructure exist to implement the domain.

They should not define it.

---

### Technology is replaceable.

The business concepts represented by the platform should remain valid even if every implementation technology changes.

---

### Behaviour precedes implementation.

Business behaviour should be modelled before selecting persistence strategies, APIs or messaging infrastructure.

---

### Architecture emerges from understanding.

Good architecture is not designed around frameworks.

It emerges from accurately modelling the business domain.

---

## Decision

The Engineering Intelligence Platform adopts a **Domain-First** development philosophy.

Business concepts, responsibilities and relationships must be understood and documented before implementation technologies are introduced.

Frameworks remain implementation details rather than architectural foundations.

---

## Consequences

This decision influences the development process for the entire project.

- Domain modelling precedes infrastructure.
- Frameworks are introduced only after the domain is established.
- The core domain remains independent of implementation technology.
- Technical decisions are evaluated against business requirements rather than convenience.

---

## Product Principles Reinforced

- Domain before technology.
- Behaviour before data.
- Understanding before implementation.
- Framework independence.

---

## Remaining Questions

Although the philosophy has been established, several implementation questions remain.

- How should the domain be organised within the codebase?
- What architectural style best supports the domain model?
- When should infrastructure become part of the implementation?
- Which technologies best support the established domain?

These questions will be answered after the core domain model has been implemented.

---

## Related Documents

- Defining the Product
- Workspace Boundary
- Knowledge Sources
- Discovering the Platform's Core Artifact
- Domain Model
- Engineering Rules

---

## Historical Note

This journal entry captures the architectural understanding at the time it was written.

Future implementation technologies may change, but the architectural philosophy documented here should remain stable unless explicitly superseded by an Architectural Decision Record (ADR).