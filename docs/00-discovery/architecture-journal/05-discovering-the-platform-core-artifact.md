# Discovering the Platform's Core Artifact

**Status:** In Progress

---

## Architectural Question

After ingesting engineering knowledge from multiple Knowledge Sources, what business artifact does the platform create that delivers value beyond the individual systems from which the knowledge originated?

Although repositories, documentation, work items and runtime systems each contain valuable engineering information, none of them individually represent how an engineering system actually works.

The objective of this discussion was to identify the platform's canonical business artifact independent of implementation technology.

---

## Background

Engineering organizations store knowledge across numerous disconnected systems.

Examples include:

- Source code repositories
- Documentation
- Work item tracking
- Database schemas
- Deployment configurations
- Runtime telemetry

Each system provides only one perspective of the engineering landscape.

No individual system possesses enough information to explain how the engineering system operates as a whole.

Before ingestion, these systems remain largely unaware of one another.

For example:

- A Jira ticket has no direct relationship with the Java method implementing it.
- A REST endpoint is disconnected from the database entities it modifies.
- Business rules exist in documentation but are not explicitly connected to implementation.

Developers reconstruct these relationships manually whenever they need to understand, troubleshoot or modify software.

---

## Alternatives Explored

### Unified Knowledge Repository

The platform stores engineering information collected from multiple systems.

#### Advantages

- Simple mental model.
- Easy to explain.

#### Limitations

- Focuses on storage rather than understanding.
- Does not explain how relationships emerge.
- Does not represent engineering behaviour.

---

### Knowledge Graph

Represent engineering artifacts as nodes connected through relationships.

#### Advantages

- Rich relationship modelling.
- Flexible navigation.
- Well suited for complex engineering systems.

#### Limitations

- Describes a technical implementation rather than a business concept.
- Different implementations may exist.
- Does not explain the value created by the platform.

---

### System Blueprint

Generate a blueprint describing the engineering system.

#### Advantages

- Easy for engineers to visualize.
- Represents overall structure.

#### Limitations

- Emphasizes static architecture.
- Does not naturally capture business intent, historical evolution or runtime behaviour.

---

### Engineering Understanding

The platform reconstructs organizational engineering understanding.

#### Advantages

- Focuses on the business outcome.
- Captures engineering intent rather than implementation.
- Independent of implementation technology.

#### Limitations

- Difficult to visualize.
- Potentially too abstract as the platform's primary business artifact.

---

### Engineering Model

Construct an internal representation describing how the engineering system behaves by combining knowledge from every connected Knowledge Source.

#### Advantages

- Vendor independent.
- Technology independent.
- Focuses on understanding rather than storage.
- Can power reasoning, search, onboarding and impact analysis.

#### Limitations

- Requires further refinement.
- Scope remains under exploration.

---

## Discussion

A key realization emerged during exploration.

The platform is not valuable because it stores engineering artifacts.

GitHub already stores source code.

Jira already stores work items.

Confluence already stores documentation.

The platform creates value by reconstructing the relationships that exist across these isolated systems.

These relationships produce an understanding that no individual system possesses.

The platform therefore creates something that did not previously exist.

It does not merely aggregate engineering artifacts.

It synthesizes them into a higher-level representation capable of supporting engineering reasoning.

Initially this artifact was described using several terms including:

- Engineering Knowledge
- Knowledge Graph
- System Blueprint
- Engineering Memory
- Engineering Understanding

Each captured part of the idea but failed to describe the business capability completely.

The current direction is the concept of an **Engineering Model**.

Rather than representing files or documents, the Engineering Model represents the engineering system itself.

---

## Key Insights

### The artifact is synthesized.

The platform's central artifact is not manually authored.

It emerges by analysing, correlating and synthesizing engineering knowledge contributed by multiple Knowledge Sources.

---

### It represents understanding rather than storage.

The Engineering Model is not another repository of engineering artifacts.

It is an interpretation of those artifacts that exposes relationships unavailable within any individual system.

---

### Reasoning consumes the artifact.

The platform's reasoning capabilities do not operate directly on repositories, documentation or work items.

Instead, they consume the synthesized representation produced after knowledge ingestion.

This enables capabilities such as:

- AI reasoning
- Impact analysis
- Dependency exploration
- Engineering search
- Developer onboarding

---

### Multiple views may emerge.

Different representations may be generated from the same underlying artifact.

Examples include:

- Architecture View
- Dependency View
- Ownership View
- Business Capability View

The Engineering Model remains the underlying representation from which these views are derived.

---

## Current Direction

Engineering Model is currently the leading candidate for describing the platform's central business artifact.

This terminology remains intentionally provisional.

The concept will continue to evolve through domain modelling and implementation before becoming part of the platform's ubiquitous language.

---

## Remaining Questions

Several important architectural questions remain unresolved.

- What information belongs inside the Engineering Model?
- Is it an Aggregate, Projection or another domain concept?
- Should the Workspace own the Engineering Model or simply reference it?
- How should the Engineering Model evolve as Knowledge Sources change?
- What responsibilities belong to the Engineering Model versus future reasoning services?
- Is the Engineering Model itself the product, or is it one representation of a deeper concept such as Engineering Understanding?

These questions will be answered through continued domain exploration and implementation.

---

## Related Documents

- Defining the Product
- Workspace Boundary
- Knowledge Sources
- Automatic Knowledge Discovery
- Domain Model
- Ubiquitous Language

---

## Historical Note

This journal entry captures the architectural understanding at the time it was written.

The concepts discussed here may evolve as the platform matures through implementation and further domain exploration.

The current architectural truth is maintained through:

- Ubiquitous Language
- Domain Model
- Architectural Decision Records (ADRs)