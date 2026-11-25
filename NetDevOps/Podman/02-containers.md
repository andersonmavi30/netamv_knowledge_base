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

## `podman run -d --name web-lab -p 127.0.0.1:8080:80 docker.io/library/nginx:stable-alpine`

```bash
podman run -d --name web-lab -p 127.0.0.1:8080:80 docker.io/library/nginx:stable-alpine
```

- **Purpose:** Create and start an Nginx lab container, exposing HTTP only on the host loopback address.
- **Arguments:** `run`: create and start; `-d`: detached; `--name web-lab`: container name; `-p 127.0.0.1:8080:80`: bind host loopback port 8080 to container port 80; `docker.io/library/nginx:stable-alpine`: fully qualified image.
- **Use case:** Serve a local test endpoint for a NetDevOps API or HTTP health-check lab; requires free host port 8080 and image access.
- **Official reference:** https://docs.podman.io/en/latest/markdown/podman-run.1.html

> Not lab-verified.

## `podman logs --tail 30 web-lab`

```bash
podman logs --tail 30 web-lab
```

- **Purpose:** Read the last 30 log lines from the named container.
- **Arguments:** `logs`: view container output; `--tail 30`: only the last 30 lines; `web-lab`: example container name.
- **Use case:** Check Nginx startup errors or HTTP access entries after a failed monitoring check; logs may contain sensitive data.
- **Official reference:** https://docs.podman.io/en/latest/markdown/podman-logs.1.html

> Not lab-verified.
