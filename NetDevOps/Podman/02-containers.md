---
tags: [podman, containers, netdevops, cli]
validation: not-lab-verified
---

# Containers and troubleshooting

[🇬🇧 English](02-containers.md) · [🇨🇴 Español](02-containers.es.md) · [↩ Podman](README.md)

**Platform:** Podman 4.x/5.x on Linux; behavior can vary by version.

## `podman ps -a`

```bash
podman ps -a
```

- **Purpose:** List running and stopped containers with state, IDs and names.
- **Arguments:** `ps`: list containers; `-a` / `--all`: include stopped containers.
- **Use case:** Locate a stopped lab service before investigating a failed network-automation job.
- **Official reference:** https://docs.podman.io/en/latest/markdown/podman-ps.1.html

> Not lab-verified.
