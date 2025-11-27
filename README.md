# Astaraxia

Astaraxia is a flexible, source–binary hybrid Linux distribution focused on transparency, configurability, and reproducibility.  
The system provides complete control over build configuration while remaining straightforward to maintain.

# Astaraxia Devs
Me

## Key Features

### Hybrid Build Model
Astaraxia allows users to install software in two ways:
- **Binary packages** for fast installation
- **Source builds** for maximum control, optimization, and reproducibility

Both modes are unified under a single package manager: **Astral**.

### Astral Package Manager
Astral is a deterministic package manager providing:
- Explicit, modular build recipes
- Dependency resolution with clear conflict detection
- Binary or source installation per package
- Fine-grained control of compile flags and features
- A readable recipe format (`.astral`)

### Transparent Build System
All package definitions are simple scripts describing:
- Source URLs  
- Build steps  
- Packaging rules  
- Dependencies  
- Optional features  
- Service integration (systemd or OpenRC)

Users can inspect and modify any part of the build process.

### Minimal Base System
Astaraxia is bootstrapped from Linux From Scratch (LFS) to guarantee:
- A clean, well-defined filesystem hierarchy  
- A reproducible toolchain and standard libraries  
- A known, traceable build order

After bootstrap, all packages—including the base—can be rebuilt through Astral.

## Directory Layout

/usr/src/astral/recipes/ # official recipe tree
/etc/astral/config # manager configuration
/var/cache/astral/src/ # cached sources
/var/cache/astral/bin/ # cached binaries
/var/lib/astral/db/ # installed package metadata


## Goals
- Provide a configurable environment without hidden build steps
- Offer a unified system for both binary and source-managed software
- Maintain long-term reproducibility through explicit metadata
- Keep the system predictable, consistent, and maintainable

## Status
Astaraxia is under active development.  
The bootstrap system (LFS-based) must be completed before the first release.

## License
Astaraxia and Astral will adopt an open-source license compatible with the upstream software they package.  
Unless otherwise specified, documentation and tooling are available under the MIT license.

