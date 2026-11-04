# Fission MC

**A different kind of Minecraft server.**

Fission is an independent Minecraft server software project built from the ground up, designed around multi-instance architecture, concurrent execution, and extensibility.

Inspired by the ideas behind Folia and the flexibility of the Paper ecosystem, Fission aims to rethink how Minecraft server software is designed, developed, and operated.

Rather than building upon an existing server implementation, Fission is developing its own foundation, avoiding direct dependencies on Minecraft's internal server implementation (NMS) while working toward compatibility with established Bukkit and Paper plugin APIs.

**We're not building another fork. We're building something new.**

---

## What is Fission?

Fission is an attempt to rethink the foundations of Minecraft server software.

Traditional server implementations have accumulated years of architectural decisions and dependencies. Fission takes the opportunity to approach these challenges differently, with a focus on modularity, concurrency, and multi-instance execution from the beginning.

Our goal is to create server software that can operate across multiple cooperating instances while maintaining a familiar development environment for plugin developers.

## Our Goals

- **Multi-instance architecture** — Design server software around multiple cooperating instances rather than treating a single server process as the only execution environment.
- **Concurrent execution** — Embrace regionized execution and parallelism, taking inspiration from Folia's approach to server performance.
- **Independent implementation** — Develop our own server architecture from the ground up instead of inheriting an existing implementation.
- **NMS independence** — Avoid direct dependencies on Minecraft's internal server implementation wherever possible.
- **Plugin compatibility** — Provide compatibility with established Bukkit and Paper plugin APIs through dedicated compatibility layers.
- **Modularity** — Keep systems independently maintainable, extensible, and clearly separated.
- **Performance & scalability** — Build with modern hardware and increasingly demanding Minecraft environments in mind.

## Architecture & Compatibility

Fission is being developed with a clear separation between its internal implementation and external compatibility interfaces.

Our intention is to avoid coupling the core implementation to Minecraft's internal classes and implementation details.

Where compatibility requires it, dedicated layers may provide access to existing Bukkit and Paper APIs, including backwards-compatibility implementations where necessary.

This allows Fission to pursue an independent architecture without abandoning the existing Minecraft plugin ecosystem.

## Team & Governance

Fission MC is jointly owned and maintained by two project owners.

### Project Owners

| Member | Role |
|---|---|
| [RATR2](https://github.com/RATR2) | Co-Owner |
| [Al3xSk1](https://github.com/Al3xSk1) | Co-Owner |

Both Co-Owners share equal ownership and overall responsibility for Fission MC, including project direction, governance, infrastructure, and long-term development.

### Maintainer Roles

Fission uses a structured maintainer hierarchy to establish clear responsibilities and ownership across the project.

| Role | Responsibilities |
|---|---|
| **Co-Owner** | Equal project ownership, governance, and overall leadership. |
| **Core Maintainer** | Oversees core repositories, reviews, code quality, and releases across the project. |
| **Technical Lead** | Oversees the technical direction and development of an assigned subsystem. |
| **Maintainer** | Maintains assigned repositories or components, reviews contributions, and handles issue management. |
| **Contributor** | Contributes code, documentation, testing, and improvements. |
| **Community Member** | Participates in discussions, testing, feedback, and community support. |

### Technical Leadership

As the project develops, technical ownership may be divided into specialized areas:

- **Core & Architecture** — Foundational systems, server lifecycle, and internal architecture.
- **Execution & Scheduling** — Regionized execution, threading, task scheduling, and concurrency.
- **Networking & Protocol** — Network connections, protocol handling, and player sessions.
- **World & Chunk Systems** — World management, chunk loading, entities, and persistence.
- **Compatibility** — Bukkit/Paper APIs and backwards-compatibility implementations.
- **Build & Infrastructure** — Build systems, CI/CD, development tooling, and project infrastructure.

Technical Leads are responsible for their assigned areas while working collaboratively with the wider maintenance team.

### Governance Principles

- Both Co-Owners hold equal project authority.
- Maintainers are trusted to make decisions within their assigned responsibilities.
- Technical decisions should prioritize maintainability, stability, and architectural consistency.
- Significant architectural changes should involve the relevant technical leads and maintainers.
- Contributions should be reviewed fairly and constructively.

## Repositories

Fission is developed as an evolving ecosystem of components and supporting projects.

Explore our organization repositories to follow development, discover individual components, and contribute.

Repositories and their responsibilities will be documented here as the project takes shape.

## Contributing

We welcome contributions from developers interested in improving Minecraft server software.

Whether you're working on core functionality, compatibility, performance, documentation, or tooling, contributions are appreciated.

Before contributing:

1. Explore the relevant repository.
2. Review its contribution guidelines.
3. Check existing issues and discussions.
4. Submit changes through a pull request.
5. Be prepared to discuss implementation details and design decisions.

Please report bugs and feature requests through the appropriate repository's issue tracker.

## Acknowledgements

Fission recognizes and appreciates the work of the wider Minecraft server development community.

In particular, we acknowledge the contributions of the Bukkit, Spigot, Paper, and Folia projects, whose work has helped shape the ecosystem in which Fission is being developed.

Fission is an independent project and is not an official continuation or fork of these projects.

---

**Fission MC**

*Built from the ground up. Designed for what comes next.*
