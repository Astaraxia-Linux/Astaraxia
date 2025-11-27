# Astaraxia  
*A flexible, source–binary hybrid Linux distribution for transparency, configurability, and reproducibility*

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
(what Astaraxia is, what makes it special compared to other distros)

## Key Features  
- Hybrid build model: binary and source packages via Astral  
- Transparent build recipes (source URLs, build steps, packaging rules, dependencies, options)  
- Minimal base system from LFS, fully rebuildable  
- Fine-grained configuration, reproducibility, clean toolchain  

## Status  
Currently bootstraping via LFS (CH8, GCC 15.2.0), no core packages yet (or list which are ready) — under active development

## Installation / Bootstrapping  
**This is just the idea, gonna make a minimal iso soon**
### Prerequisites  
- Host system requirements: x86_64 CPU (or list), RAM, disk space, Internet  
- Required tools (e.g. a working shell, ability to compile)  

### Steps  
1. Download and extract LFS sources …  
2. Follow LFS book chapter 1–8 (or link)  
3. Once you have a minimal toolchain: run `…`  
4. Install Astral (from source or binary) — `…`  
5. Use Astral to install bootstrap packages:  
   ```sh
   astral -c base-system  # compile and install base from source  
   ```  
6. (Optional) switch to desired init system: systemd / OpenRC  

## Usage Examples  
```sh
# Install binary package  
astral -s vim  

# Compile and install from source (with custom flags)  
astral -c firefox  

# Remove package with dependencies  
astral -r package_name  

# Remove just package  
astral -R package_name  

# Upgrade all installed packages  
astral -y  
```  

## Configuration  
Describe config file `/etc/astral/config`, sample contents, how to override default flags, choose compile options, enable/dis­able optional features, select init system, etc.

## Directory Layout  
```
/usr/src/astral/recipes/      # official recipe tree  
/etc/astral/config            # manager configuration  
/var/cache/astral/src/        # cached source archives  
/var/cache/astral/bin/        # cached binary packages  
/var/lib/astral/db/           # installed package metadata  
```  

## Goals  
- Provide a fully transparent build system — no hidden steps  
- Offer unified package management (binary + source)  
- Preserve reproducibility with explicit metadata  
- Keep the system predictable, clean, and maintainable  

## Roadmap / TODO  
- Finish LFS bootstrap (CH: ___)  
- Provide core packages: kernel, glibc (or alternate libc), shell, basic utilities  
- Add support for optional init systems (systemd, OpenRC)  
- Write documentation: installation guides, troubleshooting, package recipe standards  
- Make first release, tag it, publish binary package repository  
- Minimal iso
  
## License  
Documentation and tooling under MIT license. For bundled packages, upstream licenses apply.  
