---
tags: [podman, containers, netdevops, cli]
validation: not-lab-verified
---

# Podman CLI and host information

[🇬🇧 English](01-basics.md) · [🇨🇴 Español](01-basics.es.md) · [↩ Podman](README.md)

**Platform:** Podman 4.x/5.x on Linux; compatibility varies by release.

## `podman --version`

```bash
podman --version
```

- **Purpose:** Display the installed Podman version before running automation.
- **Arguments:** `--version`: prints the version and exits; read-only.
- **Use case:** Check Podman's version on a NetDevOps lab VM before running containers.
- **Official reference:** https://docs.podman.io/en/latest/markdown/podman.1.html

> Not lab-verified.

## `podman info`

```bash
podman info
```

- **Purpose:** Inspect Podman's host, storage, runtime and registries configuration.
- **Arguments:** `info`: display host and runtime configuration; read-only. Output can reveal host paths and registry details.
- **Use case:** Verify rootless mode, storage driver and OCI runtime before deploying a network automation container.
- **Official reference:** https://docs.podman.io/en/latest/markdown/podman-info.1.html

> Not lab-verified.

## `podman images`

```bash
podman images
```

- **Purpose:** List locally stored images, repositories, tags, IDs and sizes.
- **Arguments:** `images`: list local images; read-only.
- **Use case:** Confirm a Python or Ansible execution image is already available before an offline lab.
- **Official reference:** https://docs.podman.io/en/latest/markdown/podman-images.1.html

> Not lab-verified.
