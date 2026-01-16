# NTUX ARCH REPOSITORY
### Custom Arch Linux Package Repository for NTUX OS
**Developed and maintained at NIELIT Imphal**

---

## Overview

**ntux-arch-repo** is the official custom Arch Linux package repository for **NTUX OS**, a research- and development-oriented Linux distribution focused on modern workflows, clean design, and reproducible system builds.

This repository hosts **custom-built Arch packages** that are either:
* Not available in the official Arch repositories.
* Patched or customized specifically for NTUX OS.
* Built to support the NTUX installer, desktop environment, or internal tooling.

All packages follow **Arch Linux packaging standards** and are built using `makepkg` inside a clean Arch Linux build environment.

---

## Repository Structure

```text
ntux-arch-repo/
└── x86_64/
    ├── *.pkg.tar.zst      # Binary packages
    ├── ntux.db            # Repository database
    └── ntux.files         # File index
Architecture currently supported: x86_64Packages IncludedPackage NameDescriptioncalamaresDistribution-independent system installer used by NTUX OScalamares-debug(Optional) Debug symbols for CalamaresNote: Debug packages are not required for normal installation and are intended for developers and debugging builds only.Usage (Pacman Configuration)To use this repository on an Arch-based system or inside an NTUX ISO build environment, add the following to /etc/pacman.conf:Ini, TOML[ntux]
SigLevel = Optional TrustAll
Server = file:///path/to/ntux-arch-repo/$arch
Then sync and verify:Bash# Sync the database
sudo pacman -Sy

# Verify package availability
pacman -Sl ntux
Building PackagesAll packages in this repository are built using a standardized workflow to ensure consistency:Environment: Arch Linux using makepkg (Non-root user).Consistency: Clean, reproducible build environments (e.g., Docker or Arch containers).General Workflow:Bash# Build the package
makepkg -sf

# Add to the repository database
repo-add ntux.db.tar.gz *.pkg.tar.zst
Debug symbol packages are generated automatically when applicable.Design GoalsReproducibility: Minimal, clean, and reproducible system builds.Portability: Offline-install friendly and compatible with archiso.User Experience: Installer-first workflow using Calamares.Modern Aesthetics: Designed for custom desktops (specifically Hyprland-based environments).Intended UseThis repository is strictly intended for:NTUX OS ISO builds and live environments.Internal development and testing at NIELIT Imphal.Educational and research deployments.It is not intended to replace the official Arch Linux repositories.Repository DetailsMaintainer: Khuraijam GunindroInstitution: National Institute of Electronics and Information Technology (NIELIT), ImphalStatus: ActiveTarget OS: NTUX OS (Arch-based)License: Packages retain original upstream licenses; configuration is for educational use.
