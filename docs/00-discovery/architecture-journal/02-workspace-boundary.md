# Discovering the Workspace Boundary

**Status:** Accepted

---

## Architectural Question

What should be the fundamental business boundary of the Engineering Intelligence Platform?

Before any engineering knowledge can be imported or reasoned upon, the platform requires a logical boundary that defines ownership, collaboration, isolation, and governance.

The challenge was determining what that boundary should represent.

---

## Background

Software organizations vary significantly in structure.

Examples include:

- Individual developers
- Startups
- Mid-sized engineering teams
- Large enterprises
- Consulting companies serving multiple clients

The chosen boundary needed to support all of these use cases without leaking organizational assumptions into the domain model.

A consulting company, for example, may build software for multiple clients, each requiring strict isolation of engineering assets due to contractual and compliance obligations.

Likewise, an independent developer should be able to use the platform without belonging to an organization.

---

## Alternatives Explored

### Organization

Initially, Organization appeared to be the natural top-level entity.

**Advantages**

- Familiar concept.
- Represents most companies.

**Limitations**

- Assumes every user belongs to an organization.
- Cannot naturally model consulting companies serving multiple independent clients.
- Risks mixing engineering knowledge across isolated domains.
- Too closely tied to company structure rather than engineering ownership.

---

### Repository

Repositories already represent engineering assets.

**Advantages**

- Familiar to developers.
- Naturally maps to source code.

**Limitations**

- Represents only source code.
- Ignores documentation, work items, architecture, runtime systems and other engineering artifacts.
- Too granular to act as the primary business boundary.

---

### Project

Project was considered as a more generic abstraction.

**Advantages**

- Common engineering terminology.

**Limitations**

- Different vendors define projects differently.
- Does not clearly express ownership or security boundaries.
- Ambiguous across engineering tools.

---

### Workspace

Workspace emerged as a technology-independent business concept.

**Advantages**

- Represents ownership rather than company structure.
- Supports individuals, startups and enterprises equally well.
- Provides a natural collaboration boundary.
- Establishes a security and data isolation boundary.
- Remains independent of any external platform.

**Trade-offs**

- Requires a precise domain definition.
- Must remain independent of imported engineering knowledge.

---

## Discussion

An important realization emerged during the discussion.

The platform is not fundamentally modeling organizations.

It is modeling **isolated engineering domains**.

A Workspace is therefore not simply a container for files or repositories.

It is the logical boundary within which engineering understanding is constructed, governed, and shared.

This abstraction naturally accommodates multiple usage patterns.

For example:

- An individual developer may own a single Workspace.
- A startup may operate entirely within one Workspace.
- A large enterprise may create multiple Workspaces representing independent engineering domains.
- A consulting company may create one Workspace per client to guarantee complete isolation of engineering knowledge.

The concept remains stable regardless of organizational structure.

---

## Key Insights

### Workspace is a business concept.

A Workspace exists independently of databases, repositories, cloud infrastructure or deployment architecture.

It is a domain concept rather than a technical implementation.

---

### Workspace defines ownership.

Engineering resources are associated with a Workspace because the Workspace owns the engineering domain, not because it stores the resources themselves.

---

### Workspace exists before knowledge.

A newly created Workspace contains no engineering knowledge.

Importing repositories, documentation or work items enriches the Workspace but does not define it.

This realization prevented the Workspace definition from depending on future platform capabilities.

---

### Workspace is the primary business boundary.

Security, collaboration, ownership and lifecycle all originate at the Workspace level.

Future authorization, billing and governance models are expected to align with this boundary.

---

## Decision

Workspace becomes the primary ownership, collaboration and security boundary of the Engineering Intelligence Platform.

All engineering knowledge imported into the platform belongs to exactly one Workspace.

Knowledge Sources are connected to a Workspace, and engineering understanding is constructed within that boundary.

---

## Consequences

This decision establishes the foundation for the platform's domain model.

- Knowledge Sources belong to a Workspace.
- Members collaborate within a Workspace.
- Engineering understanding is isolated by Workspace.
- Authorization is expected to be enforced at the Workspace level.
- Future enterprise capabilities can build upon the Workspace abstraction without changing the core domain.

---

## Remaining Questions

Several important questions remain unresolved.

- Should the Engineering Model be owned by the Workspace or referenced by it?
- How should knowledge behave when a Knowledge Source is disconnected?
- Should Workspaces support hierarchical relationships in future versions?
- What billing model should eventually map to Workspaces?

These questions remain intentionally open until additional domain exploration is completed.

---

## Related Documents

- Defining the Product
- Ubiquitous Language
- Domain Model
- Future ADR: Workspace as the Primary Business Boundary