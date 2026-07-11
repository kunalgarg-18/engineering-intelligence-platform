# Automatic Knowledge Discovery

**Status:** Accepted

---

## Architectural Question

Should engineers manually decide which engineering artifacts are imported into the platform, or should the platform automatically discover and ingest everything it can access?

The objective of this discussion was to determine how the onboarding experience should align with the core value proposition of the Engineering Intelligence Platform.

---

## Background

Engineering knowledge within an organization is inherently fragmented.

A typical engineering organization maintains information across multiple systems including:

- Source code repositories
- Documentation platforms
- Work item tracking systems
- Deployment infrastructure
- Runtime observability platforms

Traditionally, onboarding tools require users to manually configure what should be imported.

Examples include:

- Selecting repositories
- Choosing projects
- Configuring folders
- Defining inclusion and exclusion rules

Although configurable, these approaches require engineers to perform the organizational work that the platform itself claims to automate.

This prompted a fundamental question:

**Should engineers organize engineering knowledge, or should the platform?**

---

## Alternatives Explored

### Manual Import Scope

Users explicitly select repositories, projects or engineering resources before ingestion begins.

#### Advantages

- Reduced processing cost.
- Faster initial imports.
- Greater user control.

#### Limitations

- Higher onboarding friction.
- Incomplete engineering understanding.
- Depends on users already knowing what is important.
- Risks missing critical relationships between engineering artifacts.

---

### Automatic Discovery

The platform automatically imports every engineering artifact available through connected Knowledge Sources.

#### Advantages

- Zero onboarding friction.
- Maximizes engineering coverage.
- Enables richer relationship discovery.
- Demonstrates platform capability immediately.

#### Limitations

- Longer initial processing.
- Increased infrastructure cost.
- Requires scalable ingestion architecture.

---

## Discussion

During exploration, an important realization emerged.

The platform's value is not derived from storing repositories.

Its value comes from reconstructing engineering understanding.

Requesting users to manually curate engineering artifacts shifts the burden of understanding back onto the engineer.

This contradicts the product's fundamental purpose.

Another consideration involved organizations with hundreds or thousands of repositories.

Initially, selective importing appeared attractive.

However, this introduced an important risk.

Users cannot reliably determine which repositories are relevant because they often do not know the complete dependency landscape themselves.

Historical repositories, archived services and shared libraries may all contribute valuable engineering context.

A manually curated import could therefore produce an incomplete or misleading Engineering Model.

---

## Key Insights

### The platform should perform organizational work.

The Engineering Intelligence Platform exists to reduce cognitive overhead rather than increase it.

Engineers should not be required to organize engineering knowledge before experiencing the platform's value.

---

### Completeness creates trust.

Importing all accessible engineering artifacts allows the platform to demonstrate a comprehensive understanding of an engineering organization.

Customers gain confidence when previously forgotten repositories, documentation and dependencies become visible.

---

### Missing information is more dangerous than extra information.

Incomplete engineering knowledge can produce incorrect reasoning.

Additional information can later be prioritised or weighted without losing valuable historical context.

---

### Optimisation should follow understanding.

The MVP should optimise for correctness and completeness.

Future versions may optimise processing order, prioritisation and relevance without changing the underlying product philosophy.

---

## Decision

The MVP will automatically discover and import all engineering artifacts accessible through connected Knowledge Sources.

Users are not required to manually define an import scope before the platform begins constructing engineering understanding.

Future versions may introduce intelligent prioritisation, filtering or weighting strategies, but these should remain platform-driven rather than user-driven wherever possible.

---

## Consequences

This decision establishes several long-term architectural implications.

- Knowledge Sources initiate automatic discovery.
- Import pipelines must support large-scale ingestion.
- Engineering understanding should evolve incrementally as new artifacts become available.
- AI reasoning benefits from a more complete representation of the engineering system.
- Product onboarding focuses on demonstrating value rather than collecting configuration.

---

## Product Principles Reinforced

- Infer whenever possible.
- Preserve engineering understanding.
- Optimise for understanding before optimisation.
- Reduce cognitive load for engineers.

---

## Remaining Questions

Several implementation questions remain open.

- How should ingestion progress be communicated to users?
- Should reasoning become available before the entire import completes?
- How should inactive or archived engineering artifacts influence the Engineering Model?
- How should future prioritisation algorithms determine artifact importance?

---

## Related Documents

- Defining the Product
- Workspace Boundary
- Product Principles
- Knowledge Sources
- Future ADR: Automatic Knowledge Discovery