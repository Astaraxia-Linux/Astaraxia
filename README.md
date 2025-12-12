# Astaraxia

*A flexible, source-based Linux distribution that Aims for transparency, configurability, and reproducibility.*

> **Warning:**
> Astaraxia is currently in a very early stage. The distribution and build system **do not exist in a usable form yet**. Proceed at your own existential risk.

I'm just a single dev with too many ambitions and too little time. If I succeed, you'll see it here; if I fail, well, blame entropy.

## Table of Contents

* [Overview](#overview)
* [Key Features](#key-features)
* [Status](#status)
* [Installation / Bootstrapping](#installation--bootstrapping)
* [Configuration](#configuration)
* [Directory Layout](#directory-layout)
* [Goals](#goals)
* [Astral Philosophy & Inspiration](#astral-philosophy--inspiration)
* [Roadmap / TODO](#roadmap--todo)
* [Contributing](#contributing)
* [License](#license)

## Overview

Astaraxia is a Linux distribution designed around a unified hybrid package model. It aims to give users full control over their system by allowing both **binary installations** (hopefully) and fully **transparent source builds** via a custom package manager called **Astral**.

While inspired by source-based distributions, Astaraxia intends to remain straightforward to maintain, predictable in behavior, and fully reproducible. The project is currently in the planning phase. Also, no ISO exists yet, so don’t go looking for it.

## Key Features

Planned features include:

* Hybrid build model: install packages by compiling from source or using binaries (your choice)
* Plain, inspectable build recipes (hackers love this, and yes—even your two-year-old can read them without problems)
* Minimal base system bootstrapped via Linux From Scratch (yes, really)
* Deterministic, reproducible build pipeline
* Unified package manager (Astral) for all software, including the base system

Some features are **not implemented yet**, because I’m still dreaming about them.

## Status

Astaraxia is *not* a functional distribution. Currently:

* Base system bootstrapping: LFS chapters 1–8 completed
* Astral package manager: partially implemented (the fun part)
* Initial core packages: mostly planned, some built
* ISO release: non-existent

## Installation / Bootstrapping - STAGE 1

Astaraxia cannot be installed yet. This section describes the *planned* bootstrap process.

### Prerequisites

* Electricity (optional)
* x86_64 CPU
* ≥8GB RAM (compiling takes a toll on your sanity)
* ~25GB free disk
* Working Linux system with build tools
* Internet access (because wget and Astral *are* your friends)

### Planned Steps

1. Complete LFS Chapters 1–8 to build the initial toolchain. - DONE
2. Configure `/etc`, `/usr`, kernel, etc. - PARTIALLY DONE
3. Build the Astral package manager. - 1/4
4. Use Astral to install core packages and build the base system.
5. Init system: systemd (or something resembling it)

Steps may evolve as I lose sleep, every single day :3.

## Configuration

Planned configuration will be stored in:

```
/etc/astral/config/
```

Expected options:

* Default source/binary behavior
* Global CFLAGS / CXXFLAGS / LDFLAGS
* CCACHE
* Repository locations (official + user-defined)
* Parallel build settings
* Feature toggles for optional dependencies
* Init system selection
* Cache locations and cleanup policies

## Directory Layout

Planned filesystem layout:

```
/usr/src/astral/recipes/      # official package recipes  
/etc/astral/config/           # system-level configuration
/etc/astral/config/$HOME/     # $HOME configuration
/var/cache/astral/src/        # cached source archives  
/var/cache/astral/bin/        # cached binary packages  
/var/lib/astral/db/           # installed package metadata  
/var/log/astral/              # logs for build failures and installs
```

## Goals

* Fully transparent build system
* Unified package management for source and binaries
* Maintain reproducibility with auditable metadata
* Keep the system minimal, predictable, rollbackable, and maintainable
* Allow users to fully rebuild or inspect any component
* Avoid unnecessary abstractions, because abstraction is betrayal

## Astral Philosophy & Inspiration

Astaraxia’s package manager, Astral, is heavily influenced by three distros I actually admire and daily-drive:

| Trait                            | Arch/Gentoo | NixOS | Astral / Astaraxia |
| -------------------------------- | ----------- | ----- | ------------------ |
| Minimal, hackable system         | ✅           | ⚠️    | ✅                  |
| Predictable builds               | ✅           | ✅     | ✅                  |
| Source-based control             | ⚠️          | ⚠️    | ✅                  |
| Binary convenience               | ⚠️          | ✅     | 🔧 Planned         |
| Rollbacks / transactional safety | ⚠️          | ✅     | 🔧 Planned         |
| Declarative config               | ⚠️          | ✅     | 🔧 Planned         |
| Package recipes / ebuild-like    | ✅           | ⚠️    | ✅                  |

In short: Astral takes the **predictability and minimalism of Gentoo/Arch**, and sprinkles in **Nix-style rollback dreams**. All while staying painfully transparent and POSIX-compliant. Also, rewriting it in Rust for speed? Never happening.

## Roadmap / TODO

* Finish Linux From Scratch bootstrap (current: Chapter 8) - DONE
* Implement Astral package manager (CLI + DB + recipe parser) - PARTIAL
* Define recipe specification format - DONE
* Build initial core packages (toolchain, libc, shell, base utilities) - PARTIAL
* Add support for init systemd, openrc or sysV
* Provide documentation and usage guides - PARTIAL
* Prepare a minimal bootable ISO
* Publish official binary package repository
* Create developer documentation and naming conventions

## Contributing

Contributions, ideas, and discussions are welcome once core development begins. Guidelines will be added after the initial repository structure is finalized.

## License

Documentation and tooling are planned to be licensed under the MIT License. Upstream packages retain their respective licenses.
