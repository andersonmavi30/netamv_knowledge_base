---
tags: [docker, containers, netdevops, containers]
validation: not-lab-verified
---

# Container lifecycle

[🇬🇧 English](01-containers.md) · [🇨🇴 Español](01-containers.es.md) · [↩ Docker](README.md)

## `docker ps -a --filter "name=apache"`

```bash
docker ps -a --filter "name=apache"
```

- **Purpose:** List containers (including stopped) matching apache.
- **Arguments:** -a: include stopped; --filter name=: partial name match.
- **Use case:** Find a specific lab container before changes.

## `docker run -d --name apache -p 127.0.0.1:8080:80 httpd:2.4`

```bash
docker run -d --name apache -p 127.0.0.1:8080:80 httpd:2.4
```

- **Purpose:** Create and start an Apache container from the official image.
- **Arguments:** -d: detached; --name: container name; -p: host IP:host port:container port.
- **Use case:** Open http://localhost:8080 in your browser.
- **Caution:** This uses `httpd:2.4`, not the nonexistent default `apache` image; bind to localhost for a lab.

## `docker stop apache`

```bash
docker stop apache
```

- **Purpose:** Gracefully stop the selected container.
- **Arguments:** apache: name or container ID.
- **Use case:** Stop Apache before maintenance.

## `docker start apache`

```bash
docker start apache
```

- **Purpose:** Start an existing stopped container.
- **Arguments:** apache: name or ID.
- **Use case:** Resume the lab after maintenance.

## `docker kill apache`

```bash
docker kill apache
```

- **Purpose:** Forcefully terminate a running container.
- **Arguments:** kill: sends SIGKILL by default; apache: target.
- **Use case:** Use only if the container does not respond to stop.
- **Caution:** May interrupt writes; prefer docker stop.

## `docker rename apache apache-lab`

```bash
docker rename apache apache-lab
```

- **Purpose:** Rename an existing container.
- **Arguments:** Old name and new name.
- **Use case:** Distinguish a test service from production.

## `docker exec -it apache-lab /bin/sh`

```bash
docker exec -it apache-lab /bin/sh
```

- **Purpose:** Open an interactive shell in a running container.
- **Arguments:** -i: interactive; -t: terminal; /bin/sh: widely available shell.
- **Use case:** Check files and running processes inside Apache.
- **Caution:** Use `/bin/bash` instead when the image includes it; `-ti` and `-it` are equivalent.

## `docker rm -f apache-lab`

```bash
docker rm -f apache-lab
```

- **Purpose:** Force-remove a container, including a running one.
- **Arguments:** -f: force stop and remove; target name.
- **Use case:** Clean up a disposable lab container.
- **Caution:** Destructive: confirm its name and persistent volumes before use.

> Reference examples. Verify container names/IDs, ports and state before removing or interrupting services.

[Docker CLI reference](https://docs.docker.com/reference/cli/docker/)
