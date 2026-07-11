# Ubiquitous Language

## Purpose

The Ubiquitous Language defines the shared business vocabulary used throughout the Engineering Intelligence Platform.

Its purpose is to establish a common language between engineers, architects, AI assistants, and future contributors.

Every business concept within the platform should have a single, precise definition.

These definitions represent the **current architectural truth** of the platform and evolve as the domain matures.

Unlike the Architecture Journal, which captures the evolution of ideas, this document captures the concepts that are currently agreed upon.

---

# Workspace

## Definition

A Workspace is the primary ownership, collaboration, and security boundary of the Engineering Intelligence Platform.

It represents an isolated engineering domain within which engineering knowledge is imported, organized, connected, and understood.

A Workspace exists independently of any imported engineering knowledge.

---

## Responsibilities

A Workspace is responsible for:

- Establishing ownership of engineering knowledge.
- Defining collaboration boundaries.
- Managing connected Knowledge Sources.
- Isolating engineering understanding from other Workspaces.
- Governing the lifecycle of engineering resources.

---

## What it is NOT

A Workspace is not:

- A Git repository
- A software project
- A deployment environment
- A source code directory
- A GitHub organization
- A team

Although a Workspace may contain or reference these concepts, none of them define a Workspace.

---

## Examples

Examples include:

- A solo developer's personal workspace.
- A startup's engineering workspace.
- A consulting company's client workspace.
- An enterprise business unit.

---

## Relationships

A Workspace:

- owns Knowledge Sources.
- contains Members.
- governs engineering understanding.
- isolates engineering domains.

---

## Lifecycle

A Workspace may be:

- Created
- Configured
- Connected to Knowledge Sources
- Continuously enriched
- Archived
- Deleted

---

# Knowledge Source

## Definition

A Knowledge Source is an external system capable of contributing engineering knowledge to a Workspace.

Knowledge Sources are vendor-independent business concepts.

GitHub, Jira, Confluence, Slack and future integrations are implementations of the Knowledge Source concept rather than domain concepts themselves.

---

## Responsibilities

A Knowledge Source is responsible for:

- Providing engineering knowledge.
- Initiating knowledge import.
- Supporting synchronization.
- Contributing engineering artifacts.
- Enriching the platform's understanding of an engineering system.

---

## What it is NOT

A Knowledge Source is not:

- GitHub
- GitLab
- Jira
- Confluence
- Slack

These are vendor-specific implementations.

---

## Examples

Knowledge Sources include:

- Source code management platforms.
- Documentation platforms.
- Work item management systems.
- Runtime observability platforms.
- Communication platforms.

---

## Relationships

A Knowledge Source:

- belongs to one Workspace.
- contributes engineering artifacts.
- participates in knowledge synchronization.
- enriches the platform's core artifact.

---

## Lifecycle

A Knowledge Source may be:

- Connected
- Authenticated
- Imported
- Synchronized
- Disconnected
- Removed

---

# Platform Core Artifact

## Definition

The platform's central business artifact remains under active domain exploration.

The current leading candidate is **Engineering Model**.

This terminology remains intentionally provisional until validated through implementation.

---

## Responsibilities

**TODO**

---

## What it is NOT

**TODO**

---

## Examples

**TODO**

---

## Relationships

**TODO**

---

## Lifecycle

**TODO**

---

# Artifact

## Definition

An Artifact is a discrete unit of engineering knowledge imported from a Knowledge Source.

Artifacts represent the raw inputs used to construct the platform's understanding of an engineering system.

Examples include source code files, documentation pages, work items, database schemas, deployment manifests and runtime logs.

---

## Responsibilities

An Artifact is responsible for:

- Representing imported engineering knowledge.
- Preserving provenance.
- Participating in relationship discovery.
- Contributing to the platform's core artifact.

---

## What it is NOT

An Artifact is not:

- The platform's understanding.
- A business capability.
- An implementation decision.

Artifacts are inputs rather than outputs.

---

## Examples

Examples include:

- Java source file
- REST controller
- Jira ticket
- Confluence document
- SQL migration
- Kubernetes manifest
- Runtime log

---

## Relationships

An Artifact:

- originates from one Knowledge Source.
- belongs to one Workspace.
- participates in relationship discovery.
- contributes to the platform's core artifact.

---

## Lifecycle

An Artifact may be:

- Imported
- Classified
- Linked
- Updated
- Archived
- Removed