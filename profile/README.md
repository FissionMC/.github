<div align="center">

# Fission MC

[![Stars](https://img.shields.io/github/stars/FissionMC/FissionMC?style=for-the-badge&logo=github)](https://github.com/FissionMC/FissionMC/stargazers)
[![Issues](https://img.shields.io/github/issues/FissionMC/FissionMC?style=for-the-badge&logo=github)](https://github.com/FissionMC/FissionMC/issues)
[![Last commit](https://img.shields.io/github/last-commit/FissionMC/FissionMC?style=for-the-badge&logo=github)](https://github.com/FissionMC/FissionMC/commits/main)
[![Commits](https://img.shields.io/github/commit-activity/m/FissionMC/FissionMC?style=for-the-badge&logo=github&label=commits%2Fmonth)](https://github.com/FissionMC/FissionMC/graphs/commit-activity)
[![Minecraft](https://img.shields.io/badge/minecraft-26.3-blue?style=for-the-badge)](#status)
[![Language](https://img.shields.io/badge/kotlin-jvm-purple?style=for-the-badge&logo=kotlin)](https://github.com/FissionMC/FissionMC)
[![Status](https://img.shields.io/badge/status-in--development-yellow?style=for-the-badge)](#status)

> One Minecraft world, many servers.
> Fission splits a world across several cooperating backend processes behind a master that keeps the player's connection alive, so players cross between them without a loading screen.

</div>

---

## What is Fission

Fission is a Minecraft server written in Kotlin for the JVM. It runs the real vanilla server code (Mojang-mapped, loaded through its own class loader and patched at runtime with Mixin), ports Paper's Craft layer so Bukkit and Paper plugins keep working, and adds a built-in network layer on top.

Instead of squeezing more out of one process, Fission shards the world in space. Each region of the world belongs to its own backend server, and a **master** sits in front of them:

- the master terminates the real client connection and relays it to whichever backend owns the player's position,
- backends replicate block changes, entities, world settings and chunk data through the master,
- a player (and their pets, leashed mobs, riders) walks from one backend to the next without the client ever reloading the level.

Each backend can stay single-threaded, and you add capacity by adding backends.

## How it fits together

| Piece | What it does |
|---|---|
| **Master** | Accepts client connections, owns the chunk store and chunk leases, orders replication, owns world settings (time, weather, game rules), runs the safety layer |
| **Backends** | Paper-compatible servers that tick only the region they own and show neighbouring regions as ghosts |
| **Regions** | The world is split per dimension into chunk-aligned rectangles, each with one owner, plus a ghost zone around every border |
| **Seamless switch** | The master rewrites entity ids on the fly (`transplant`), so a border crossing keeps the client's world and player, with no Login or Respawn |
| **Packet pipeline** | PacketEvents-style pipeline built into the network layer, not a plugin API |
| **Craft layer** | Bukkit and Paper API implementation (`org.bukkit.craftbukkit.*`) rebuilt on top of the vanilla classes |

## Status

Fission is in active development and **not ready for production**. The foundation, the node network and the master are built, and the border work (handover, ghosts, seamless switching) is being tested live.

| Milestone | State |
|---|---|
| Foundation, node network | done |
| Master, replication | working, still being hardened |
| Packet pipeline | mostly built |
| Regions and presence (borders, handover, ghosts, mob behaviour at the border) | in progress, the current focus |
| Plugin compatibility, Craft layer depth | in progress |
| Compatibility test harness, optimization, release | not started |

The full checklist is the [roadmap](https://github.com/FissionMC/FissionMC/blob/main/ROADMAP.md).

## Repositories

| Repository | What it is |
|---|---|
| [**FissionMC**](https://github.com/FissionMC/FissionMC) | The server: master, backend, protocol, Craft layer, packet pipeline, test tools |
| [**.github**](https://github.com/FissionMC/.github) | This profile |

More repositories will appear here as parts of the project are split out.

## Team

Fission MC is jointly owned and maintained by two co-owners.

| Member | Role |
|---|---|
| [RATR2](https://github.com/RATR2) | Co-Owner |
| [Al3xSk1](https://github.com/Al3xSk1) | Co-Owner |

Both co-owners share equal ownership and responsibility for project direction, governance and infrastructure. Decisions inside an area are made by the maintainers and technical leads responsible for it, and significant architectural changes involve the people who own the affected areas.

## Contributing

1. Look at the [roadmap](https://github.com/FissionMC/FissionMC/blob/main/ROADMAP.md) and the [open issues](https://github.com/FissionMC/FissionMC/issues).
2. Open an issue or discussion before large changes.
3. Send changes as a pull request and be ready to talk through the design.

Bugs and feature requests go to the issue tracker of the repository they concern.

## Acknowledgements

Fission builds on ideas from the Bukkit, Spigot, Paper and Folia projects, and on the Mixin and PacketEvents ecosystems. It is an independent project and not an official continuation or fork of any of them.

---

<div align="center">

*One world. Many servers.*

</div>
