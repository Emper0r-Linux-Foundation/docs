# Architecture overview

{% hint style="info" %}
This overview is inferred from the descriptions of the organization's repositories. Maintainers should confirm and refine it as the implementations land.
{% endhint %}

The Emper0r Linux Foundation organization is split into small, single-purpose repositories. They group naturally into six areas.

## Areas of the project

| Area                         | Repositories                                                                                                                                                               | Responsibility                                                                                       |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Packaging and distribution   | [packages](repositories/packages.md), [package-manager](repositories/package-manager.md), [devtools](repositories/devtools.md), [repo-mirror](repositories/repo-mirror.md) | Build recipes, package manager tooling, clean-chroot builds, signing, and publishing binary packages |
| Images and installation      | [stage-builder](repositories/stage-builder.md), [iso-builder](repositories/iso-builder.md), [installer](repositories/installer.md)                                         | Base rootfs tarballs, live ISOs with bootloaders and initramfs, and the CLI/TUI installer            |
| Security                     | [security-tools](repositories/security-tools.md), [hardening-configs](repositories/hardening-configs.md), [meta-tools](repositories/meta-tools.md)                         | Defensive scripts and monitors, default firewall/MAC/sysctl policy, and selectable tool bundles      |
| System defaults and branding | [defaults](repositories/defaults.md), [artwork](repositories/artwork.md)                                                                                                   | System-wide configuration and skeleton files, logos, wallpapers, boot splash, and themes             |
| Quality                      | [testing-harness](repositories/testing-harness.md)                                                                                                                         | Automated VM boot tests and CI checks                                                                |
| Project and community        | [website](repositories/website.md), [.github](repositories/dot-github.md), [docs](repositories/docs-repo.md)                                                               | Landing page and release announcements, organization profile, and this documentation                 |

## Expected flow

Based on the repository descriptions, the pieces are expected to fit together roughly like this:

1. Package recipes in `packages` are built in clean chroots and signed using the tooling in `devtools`.
2. `repo-mirror` hosts, syncs, and publishes the resulting binary packages.
3. `stage-builder` generates minimal base rootfs tarballs for manual installs, and `iso-builder` generates live ISO images with their bootloader and initramfs configuration.
4. `installer` handles partitioning, disk encryption, and bootstrapping of the system.
5. `defaults`, `hardening-configs`, and `artwork` supply the system-wide configuration, security defaults, and branding that ship with the system.
6. `security-tools` provides the defensive utilities, which `meta-tools` groups into selectable bundles.
7. `testing-harness` boots new ISOs in virtual machines and runs CI checks so that new ISOs and packages do not break existing installs.
8. `website` publishes the landing page, the list of download mirrors, and release announcements.

## Decisions still to document

Several repository descriptions name more than one option. These choices are not yet recorded and should be documented once made:

* **Package recipe format** — PKGBUILD or ebuild files (`packages`).
* **Package manager approach** — own source code, wrappers, or configuration overlays (`package-manager`).
* **Bootloader** — GRUB or systemd-boot (`iso-builder`).
* **Firewall** — nftables or ufw (`hardening-configs`).
* **Mandatory access control** — AppArmor or SELinux (`hardening-configs`).
