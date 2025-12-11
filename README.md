# Astaraxia  
*A flexible, source-based Linux distribution that Aims for transparency, configurability, and reproducibility.*

> **Warning:**  
> Astaraxia is currently in a early-stage.  
> The distribution, package manager, recipes, and build system **do not exist in a usable form yet**.  

Im a just single dev, i dont have anyone to help me with. i dont know if i can do all of this

## Table of Contents  
- [Overview](#overview)  
- [Key Features](#key-features)  
- [Status](#status)  
- [Installation / Bootstrapping](#installation--bootstrapping)  
- [Configuration](#configuration)  
- [Directory Layout](#directory-layout)  
- [Goals](#goals)  
- [Roadmap / TODO](#roadmap--todo)  
- [Contributing](#contributing)  
- [License](#license)

## Overview  
Astaraxia is a Linux distribution designed around a unified hybrid package model.  
It aims to give users full control over their system by allowing both binary installations and fully transparent source builds through a custom package manager called **Astral**.

While inspired by source-based distributions, Astaraxia intends to remain straightforward to maintain, predictable in behavior, and fully reproducible.  
The project is currently in the planning phase.

## Key Features  
Planned features include:

- Hybrid build model: install packages by compiling it from source  
- Plain, transparent build recipes that users can inspect and modify  
- Minimal base system created via Linux From Scratch  (yes the end game)
- Deterministic, reproducible build pipeline  
- Unified package manager (Astral) for all software, base system included  

Some of the features are **not implemented yet**.

## Status  
Astaraxia is *not* a functional distribution.  
The developer is currently working through BLFS.  
Once the base system is complete, initial work on Astral and package recipes will begin. - NOW

No ISO and no release currently exist.

## Installation / Bootstrapping - STAGE 1
Astaraxia cannot be installed yet.  
This section describes the *planned* bootstrap process.

### Prerequisites  
- x86_64 CPU 
- RAM suitable for compiling (8GB or More is recommended)  
- ~25GB free disk  
- A working Linux system with compilation tools  
- Internet access for sources

### Planned Steps  
1. Complete LFS Chapters 1–8 to build the initial toolchain. - DONE
2. Configure /etc, /usr, kernel and etc - PARTIALY
2. Build the Astral package manager. - 1/4
3. Use Astral to install core packages and build the base system.  
4. init system systemd.

These steps are currently placeholders and will be updated once development begins.

## Configuration
Planned configuration will be stored in: 
```
/etc/astral/config
```

Expected tunable options:
- Default source/binary behavior
- Global CFLAGS / CXXFLAGS / LDFLAGS
- CCACHE
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
- Offer unified package management for source
- Maintain reproducibility with explicit, auditable metadata
- Keep the system predictable, minimal, rollbackable and maintainable
- Allow users to fully rebuild or inspect any component
- Avoid unnecessary abstraction or hidden automation

## Roadmap / TODO
- Finish Linux From Scratch bootstrap (current: Chapter 8) DONE
- Implement Astral package manager (CLI + database + recipe parser) - DONE
- Define recipe specification format - DONE
- Build initial core packages (toolchain, libc, shell, base utilities) - DONE
- Add support for init systemd, openrc or sysV
- Provide documentation and usage guides - PARTIALY
- Prepare a minimal bootable ISO
- Publish official binary package repository
- Create developer documentation and naming conventions

## Contributing
Contributions, ideas, and discussions are welcome once core development begins.
Guidelines will be added after the initial repository structure is finalized.

## License
Documentation and tooling are planned to be licensed under the MIT License.
Upstream packages retain their respective licenses.
