---
tags: [docker, containers, netdevops, images-registry]
validation: not-lab-verified
---

# Images and registry

[🇬🇧 English](02-images-registry.md) · [🇨🇴 Español](02-images-registry.es.md) · [↩ Docker](README.md)

## `docker images --filter "reference=*apache*"`

```bash
docker images --filter "reference=*apache*"
```

- **Purpose:** List locally stored images matching apache.
- **Arguments:** --filter reference=: image name/tag pattern.
- **Use case:** Find a custom Apache image.

## `docker rmi apache:php`

```bash
docker rmi apache:php
```

- **Purpose:** Remove a locally tagged image.
- **Arguments:** rmi: image removal; apache:php: repository and tag.
- **Use case:** Clear an obsolete lab image.
- **Caution:** Destructive; containers using the image can block removal. Do not force-delete blindly.

## `docker commit apache andersonmavi30/apache:manual`

```bash
docker commit apache andersonmavi30/apache:manual
```

- **Purpose:** Create an image snapshot from a container's writable layer.
- **Arguments:** commit: container name/ID and target image:tag.
- **Use case:** Save a manual lab change to inspect later.
- **Caution:** Volumes are not captured; prefer a reproducible Dockerfile for permanent builds.

## `docker login`

```bash
docker login
```

- **Purpose:** Authenticate interactively to a container registry.
- **Arguments:** No flags: Docker Hub by default; follow the secure device/login flow.
- **Use case:** Authenticate before pushing to your namespace.
- **Caution:** Never put passwords or tokens directly in README commands.

## `docker tag apache:php andersonmavi30/apache:php`

```bash
docker tag apache:php andersonmavi30/apache:php
```

- **Purpose:** Assign a Docker Hub repository name to a local image.
- **Arguments:** tag: source image and new repository:tag.
- **Use case:** Prepare your locally built image for Docker Hub.

## `docker push andersonmavi30/apache:php`

```bash
docker push andersonmavi30/apache:php
```

- **Purpose:** Publish a tagged image to a registry.
- **Arguments:** push: fully qualified image; requires registry access.
- **Use case:** Upload the Apache/PHP lab image.
- **Caution:** Use your actual repository/namespace and avoid publishing secrets.

> Reference examples. Verify container names/IDs, ports and state before removing or interrupting services.

[Docker CLI reference](https://docs.docker.com/reference/cli/docker/)
