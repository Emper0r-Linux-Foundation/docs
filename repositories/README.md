# Repositories

The Emper0r Linux Foundation organization contains 16 repositories. Each has its own page describing its purpose and scope.

## Packaging and distribution

| Repository                            | Description                                                                        |
| ------------------------------------- | ---------------------------------------------------------------------------------- |
| [packages](packages.md)               | Monorepo of all package build recipes and custom system profiles                   |
| [package-manager](package-manager.md) | Package manager source code, wrappers, or custom config overlays                   |
| [devtools](devtools.md)               | Build-in-clean-chroot scripts, package signing tools, and repo database generators |
| [repo-mirror](repo-mirror.md)         | Scripts and CI/CD workflows to host, sync, and publish binary packages             |

## Images and installation

| Repository                        | Description                                                                 |
| --------------------------------- | --------------------------------------------------------------------------- |
| [stage-builder](stage-builder.md) | Build scripts for minimal base rootfs/stage3 tarballs for manual installs   |
| [iso-builder](iso-builder.md)     | Live ISO generation scripts, bootloaders, and initramfs configs             |
| [installer](installer.md)         | CLI/TUI utility for partitioning, disk encryption, and system bootstrapping |

## Security

| Repository                                | Description                                                                   |
| ----------------------------------------- | ----------------------------------------------------------------------------- |
| [security-tools](security-tools.md)       | In-house defensive scripts, network monitors, and hardening utilities         |
| [hardening-configs](hardening-configs.md) | Default firewall rules, AppArmor/SELinux profiles, and kernel sysctl defaults |
| [meta-tools](meta-tools.md)               | Metapackages that group defensive and auditing utilities into bundles         |

## System defaults and branding

| Repository              | Description                                                                      |
| ----------------------- | -------------------------------------------------------------------------------- |
| [defaults](defaults.md) | System-wide configs, `/etc/skel` files, shell setups, and window manager configs |
| [artwork](artwork.md)   | Logos, wallpapers, Plymouth splash screens, GRUB themes, and ASCII banners       |

## Quality

| Repository                            | Description                                                     |
| ------------------------------------- | --------------------------------------------------------------- |
| [testing-harness](testing-harness.md) | Automated VM boot tests and CI checks for new ISOs and packages |

## Project and community

| Repository               | Description                                                    |
| ------------------------ | -------------------------------------------------------------- |
| [website](website.md)    | Landing page, download mirrors list, and release announcements |
| [.github](dot-github.md) | Organization profile                                           |
| [docs](docs-repo.md)     | Source of this documentation                                   |
