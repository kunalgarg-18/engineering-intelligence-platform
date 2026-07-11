# Knowledge Sources

**Status:** Accepted

---

## Architectural Question

How should external engineering systems be represented within the Engineering Intelligence Platform?

Modern engineering organizations use a diverse ecosystem of tools to manage software development. The platform needed a domain abstraction capable of representing these systems without coupling the domain model to specific vendors or technologies.

The objective was to identify the correct business abstraction for these integrations.

---

## Background

Engineering understanding is distributed across numerous external systems.

Examples include:

- Source code management platforms
- Documentation platforms
- Work item tracking systems
- CI/CD systems
- Runtime observability platforms
- Communication platforms

Although these systems differ significantly, they all contribute information that helps explain how an engineering organization operates.

Initially, these systems were considered individually.

Examples included:

- GitHub
- Jira
- Confluence
- Slack

However, modelling each vendor independently introduced unnecessary complexity into the core domain.

---

## Alternatives Explored

### Vendor-specific Integrations

Model GitHub, Jira, Confluence and other platforms as first-class business concepts.

#### Advantages

- Familiar terminology.
- Straightforward mapping to APIs.

#### Limitations

- Couples the domain to external vendors.
- Requires new business entities for every integration.
- Makes the domain evolve whenever new tools are supported.
- Focuses on implementation rather than business meaning.

---

### Generic External Systems

Treat every external platform as an unspecified external system.

#### Advantages

- Simple abstraction.
- Technology independent.

#### Limitations

- Does not explain *why* the system exists.
- Fails to communicate what value the platform extracts.

---

### Knowledge Source

Represent every connected system as a provider of engineering knowledge.

GitHub, Jira, Confluence, Slack and future integrations become different implementations of the same business concept.

#### Advantages

- Vendor independent.
- Stable domain abstraction.
- Scales naturally as new integrations are added.
- Focuses on business value rather than technology.

---

## Discussion

During exploration, an important realization emerged.

The platform is not interested in GitHub because it is GitHub.

It is interested because GitHub contributes engineering knowledge.

The same reasoning applies to every future integration.

A repository hosting platform contributes source code.

A documentation platform contributes design intent.

A work item platform contributes business requirements and implementation history.

An observability platform contributes runtime behaviour.

Although the information differs, the business purpose remains identical.

Each system contributes knowledge required to reconstruct engineering understanding.

This insight led to a vendor-independent abstraction.

Rather than modelling individual products, the domain models a single concept:

**Knowledge Source**

---

## Key Insights

### Vendors are implementation details.

The business domain should remain stable even if engineering organizations migrate from one platform to another.

Changing from GitHub to GitLab should not require changes to the core domain model.

---

### Knowledge Sources contribute understanding.

A Knowledge Source is valuable not because of the data it stores, but because of the engineering understanding it contributes.

---

### Every Knowledge Source enriches the Engineering Model.

Knowledge Sources provide different perspectives of the same engineering system.

No single source provides complete understanding.

Engineering understanding emerges only after combining information across multiple Knowledge Sources.

---

### Knowledge Sources belong to a Workspace.

A Knowledge Source cannot exist independently.

It always contributes knowledge within the context of a single Workspace.

Ownership, permissions and lifecycle are governed by the Workspace.

---

## Decision

The platform introduces **Knowledge Source** as the canonical business abstraction representing any external system capable of contributing engineering understanding.

All external integrations will be modelled as Knowledge Sources.

Vendor-specific behaviour belongs to the infrastructure layer rather than the core domain.

---

## Consequences

This decision has several architectural implications.

- New integrations extend existing abstractions rather than introducing new domain concepts.
- The domain model remains independent of vendor APIs.
- Workspace owns the lifecycle of connected Knowledge Sources.
- Import pipelines operate against Knowledge Sources rather than individual vendors.
- AI reasoning consumes unified engineering understanding rather than vendor-specific data.

---

## Product Principles Reinforced

- Domain before technology.
- Vendor independence.
- Preserve engineering understanding.
- Behaviour over implementation.

---

## Remaining Questions

Several questions remain intentionally unresolved.

- How should authentication credentials be managed?
- How should synchronization be scheduled?
- Should Knowledge Sources support versioning?
- How should partial failures during ingestion be represented?
- What metadata should every Knowledge Source expose regardless of vendor?

These questions concern implementation and operational behaviour rather than the business abstraction itself.

---

## Related Documents

- Defining the Product
- Workspace Boundary
- Automatic Knowledge Discovery
- Ubiquitous Language
- Domain Model
- Future ADR: Knowledge Sources