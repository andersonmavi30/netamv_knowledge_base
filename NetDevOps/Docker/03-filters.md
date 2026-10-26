---
tags: [docker, containers, netdevops, filters]
validation: not-lab-verified
---

# Filtering and troubleshooting

[🇬🇧 English](03-filters.md) · [🇨🇴 Español](03-filters.es.md) · [↩ Docker](README.md)

## `docker ps -a --filter "name=cisco"`

```bash
docker ps -a --filter "name=cisco"
```

- **Purpose:** Filter containers by a name containing cisco.
- **Arguments:** --filter name=: Docker-native substring matching.
- **Use case:** Locate a Cisco lab container among many others.

## `docker ps -a --filter "status=exited"`

```bash
docker ps -a --filter "status=exited"
```

- **Purpose:** Show only stopped containers that exited.
- **Arguments:** --filter status=exited: state selector.
- **Use case:** Find lab services that unexpectedly exited.

## `docker images --filter "reference=*cisco*"`

```bash
docker images --filter "reference=*cisco*"
```

- **Purpose:** Find images with names matching cisco.
- **Arguments:** --filter reference=: wildcard-aware image reference filter.
- **Use case:** Identify cached Cisco images before cleaning up.

## `docker ps -a --format '{{.Names}}' | grep -i cisco`

```bash
docker ps -a --format '{{.Names}}' | grep -i cisco
```

- **Purpose:** Search container names with a Linux shell pipeline.
- **Arguments:** --format: return names; | grep -i: case-insensitive text search.
- **Use case:** Find Cisco-like names on a Linux host.
- **Caution:** Requires a shell with `grep` (Linux/WSL). Prefer Docker's --filter for portability.

## `docker images --format '{{.Repository}}:{{.Tag}}' | grep -i cisco`

```bash
docker images --format '{{.Repository}}:{{.Tag}}' | grep -i cisco
```

- **Purpose:** Search repository:tag lines from local images.
- **Arguments:** --format: output repository and tag; grep -i: text filter.
- **Use case:** Find image versions by vendor keyword.
- **Caution:** Shell-specific; Docker image --filter reference= is an alternative.

## `docker logs --tail 50 apache`

```bash
docker logs --tail 50 apache
```

- **Purpose:** Read the last 50 Apache container log lines.
- **Arguments:** --tail 50: last lines; apache: name or ID.
- **Use case:** Investigate why the web server failed to start.

## `docker logs apache 2>&1 | grep -i error`

```bash
docker logs apache 2>&1 | grep -i error
```

- **Purpose:** Search container logs for error lines in a Linux shell.
- **Arguments:** 2>&1: merge stderr; | grep -i: case-insensitive search.
- **Use case:** Reduce noisy logs during troubleshooting.
- **Caution:** Only works when the host shell supports grep and redirection.

> Reference examples. Verify container names/IDs, ports and state before removing or interrupting services.

[Docker CLI reference](https://docs.docker.com/reference/cli/docker/)
