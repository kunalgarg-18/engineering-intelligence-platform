# Defining the Product

**Status:** Accepted

---

## Architectural Question

What product are we actually building?

Although the project initially began as an AI-powered developer workspace, it quickly became apparent that this described only the user interface rather than the core problem the platform was solving.

The objective of this discussion was to identify the true product independent of technologies, AI models, or user interfaces.

---

## Background

Modern software organizations accumulate engineering knowledge across numerous disconnected systems.

Examples include:

- Source code repositories
- Documentation platforms
- Work item tracking systems
- Architecture documents
- Database schemas
- Deployment configurations
- Runtime logs
- Team discussions

Each system contains only a fragment of the overall engineering understanding.

As a result, developers spend significant time reconstructing context before making even small software changes.

This context often exists only in the minds of experienced engineers and is gradually lost as systems evolve and teams change.

---

## Alternatives Explored

### AI Developer Workspace

The project initially focused on creating an AI-powered workspace that would assist software engineers.

**Why it was insufficient**

This described how users would interact with the product rather than what the product fundamentally produced.

The AI interface could change without changing the actual product.

---

### Engineering Knowledge Platform

The next iteration described the product as a platform for collecting engineering knowledge.

**Why it was insufficient**

Knowledge is too broad and abstract.

The term failed to communicate what unique value the platform creates from that knowledge.

---

### Engineering Intelligence Platform

The final direction focused on transforming fragmented engineering artifacts into structured engineering understanding.

This definition describes the business capability rather than the interface through which users interact.

---

## Discussion

During multiple design discussions, an important distinction emerged.

The platform is not valuable because it stores source code, documentation, or tickets.

Existing tools already perform those tasks extremely well.

The platform becomes valuable because it reconstructs the relationships between those artifacts and produces a coherent understanding of how an engineering organization functions.

In other words:

GitHub stores code.

Jira stores work items.

Confluence stores documentation.

The Engineering Intelligence Platform explains how all of them relate to one another.

This understanding becomes the foundation for every higher-level capability the platform provides.

---

## Key Insights

Several insights fundamentally changed the direction of the product.

### The AI is not the product.

Artificial Intelligence is one consumer of the platform's understanding rather than the platform itself.

The architecture must remain valuable even if AI technologies evolve.

---

### Engineering artifacts are inputs.

Repositories, documentation, tickets, runtime systems and similar resources are not the product.

They are inputs used to construct a richer representation of the engineering system.

---

### Engineering understanding is the true asset.

The platform's long-term value lies in preserving and reconstructing organizational engineering understanding that would otherwise remain fragmented across multiple systems or locked inside individual engineers' experience.

---

### The platform should reduce cognitive load.

Engineers should not be responsible for manually organizing engineering knowledge.

The platform should infer relationships wherever possible and continuously improve its understanding as additional knowledge becomes available.

---

## Decision

The product is defined as an **Engineering Intelligence Platform**.

Its primary responsibility is to reconstruct engineering understanding from fragmented engineering artifacts and provide a unified foundation for reasoning, exploration, impact analysis, onboarding, and intelligent engineering assistance.

Artificial Intelligence is an important capability of the platform, but it is not its defining characteristic.

---

## Consequences

This decision influences every architectural decision that follows.

- AI becomes a consumer of the platform rather than its center.
- Engineering artifacts become inputs rather than products.
- Domain modelling takes precedence over framework selection.
- The platform focuses on understanding engineering systems rather than generating code.
- Product capabilities should emerge naturally from the reconstructed engineering understanding.

---

## Remaining Questions

The following questions remain under active exploration.

- What is the canonical representation of engineering understanding?
- Should the platform produce an Engineering Model, System Blueprint, or another abstraction?
- How should engineering understanding evolve as connected knowledge sources change over time?
- What responsibilities belong to the Engineering Model versus the reasoning engine?

---

## Related Documents

- Ubiquitous Language
- Domain Model
- Product Vision
- Architecture Decision Records (future)