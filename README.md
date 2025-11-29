# Astaraxia  
*A flexible, source–binary hybrid Linux distribution for transparency, configurability, and reproducibility.*

> **Warning:**  
> Astaraxia is currently an early-stage concept.  
> The distribution, package manager, recipes, and build system **do not exist in a usable form yet**.  
> NOTE THAT THIS IS A BLEEDING EDGE BRANCH

## Table of Contents  
- [Overview](#overview)  
- [Key Features](#key-features)  
- [Status](#status)  
- [Installation / Bootstrapping](#installation--bootstrapping)  
- [Usage Examples](#usage-examples)  
- [Configuration](#configuration)  
- [Directory Layout](#directory-layout)  
- [Goals](#goals)  
- [Roadmap / TODO](#roadmap--todo)  
- [Contributing](#contributing)  
- [License](#license)

## Overview  
Astaraxia is a conceptual Linux distribution designed around a unified hybrid package model.  
It aims to give users full control over their system by allowing both binary installations and fully transparent source builds through a custom package manager called **Astral**.

While inspired by source-based distributions, Astaraxia intends to remain straightforward to maintain, predictable in behavior, and fully reproducible.  
The project is currently in the planning phase.

## Key Features  
Planned features include:

- Hybrid build model: install packages as binaries or compile from source  
- Plain, transparent build recipes that users can inspect and modify  
- Minimal base system created via Linux From Scratch  
- Deterministic, reproducible build pipeline  
- Unified package manager (Astral) for all software, base system included  

These features are **not implemented yet**.

## Status  
Astaraxia is *not* a functional distribution.  
The developer is currently working through the BLFS.  
Once the base system is complete, initial work on Astral and package recipes will begin.

No ISO, no repositories, no packages, and no release currently exist.

## Installation / Bootstrapping  
Astaraxia cannot be installed yet.  
This section describes the *planned* bootstrap process.

### Prerequisites  
- x86_64 CPU 
- RAM suitable for compiling (8GB recommended)  
- ~25GB free disk  
- A working Linux system with compilation tools  
- Internet access for sources

### Planned Steps  
1. Complete LFS Chapters 1–8 to build the initial toolchain.  
2. Enter the chroot environment.  
3. Clone the Astaraxia repository.  
4. Build the Astral package manager.  
5. Use Astral to install core packages and build the base system.  
6. init system systemd.

These steps are currently placeholders and will be updated once development begins.

## Usage Examples  
Future examples for Astral might include:

```sh
astral -s vim      # install from binary
astral -c firefox  # compile from source
astral -r pkg      # remove package and its unused dependencies
astral -R pkg      # remove package only
astral -y          # upgrade all installed packages
```

## Configuration
Planned configuration will be stored in: 
```
/etc/astral/config
```

Expected tunable options:
- Default source/binary behavior
- Global CFLAGS / CXXFLAGS / LDFLAGS
- Repository locations (official + user-defined)
- Parallel build settings
- Feature toggles for optional dependencies
- Init system selection
- Cache locations and cleanup policies

## Directory Layout
Planned filesystem layout:
```
/usr/src/astral/recipes/      # official package recipes  
/etc/astral/config            # system-level configuration
/etc/astral/config/$HOME/     # $HOME configuration
/var/cache/astral/src/        # cached source archives  
/var/cache/astral/bin/        # cached binary packages  
/var/lib/astral/db/           # installed package metadata  
/var/log/astral/              # logs for build failures and installs
```
## Goals

- Provide a fully transparent build system
- Offer unified package management for both binary and source packages
- Maintain reproducibility with explicit, auditable metadata
- Keep the system predictable, minimal, and maintainable
- Allow users to fully rebuild or inspect any component
- Avoid unnecessary abstraction or hidden automation

## Roadmap / TODO
- Finish Linux From Scratch bootstrap (current: Chapter 8)
- Implement Astral package manager (CLI + database + recipe parser)
- Define recipe specification format
- Build initial core packages (toolchain, libc, shell, base utilities)
- Add support for init systemd
- Provide documentation and usage guides
- Prepare a minimal bootable ISO
- Publish official binary package repository
- Create developer documentation and naming conventions

## Contributing
Contributions, ideas, and discussions are welcome once core development begins.
Guidelines will be added after the initial repository structure is finalized.

## License
Documentation and tooling are planned to be licensed under the MIT License.
Upstream packages retain their respective licenses.
