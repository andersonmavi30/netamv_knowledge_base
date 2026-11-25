---
tags: [podman, containers, netdevops, cli, python]
validation: not-lab-verified
---

# Python virtual environments and pip in containers

[🇬🇧 English](03-python-labs.md) · [🇨🇴 Español](03-python-labs.es.md) · [↩ Podman](README.md)

**Platform:** Podman 4.x/5.x on Linux with Python 3.12 in the selected image. Python commands are not Podman subcommands.

## `podman run --rm -v "$PWD:/workspace:Z" -w /workspace docker.io/library/python:3.12-slim python -m venv .venv`

```bash
podman run --rm -v "$PWD:/workspace:Z" -w /workspace docker.io/library/python:3.12-slim python -m venv .venv
```

- **Purpose:** Create a Python virtual environment in the host project's `.venv` directory by running Python inside a temporary Podman container.
- **Arguments:** `run`: create container; `--rm`: remove after exit; `-v "$PWD:/workspace:Z"`: bind current directory with private SELinux relabel (may relabel host files); `-w /workspace`: working directory; `python -m venv .venv`: create the environment in the bind mount.
- **Use case:** From a trusted lab project directory, initialize `.venv` for a NetBox API script. On SELinux hosts, `:Z` modifies labels; host permissions and ownership require review. Use the same container image for subsequent steps; a venv created in a container is not necessarily portable to the host.
- **Official reference:** https://docs.podman.io/en/latest/markdown/podman-run.1.html

> Not lab-verified.

## `podman run --rm -v "$PWD:/workspace:Z" -w /workspace docker.io/library/python:3.12-slim .venv/bin/python -m pip install requests`

```bash
podman run --rm -v "$PWD:/workspace:Z" -w /workspace docker.io/library/python:3.12-slim .venv/bin/python -m pip install requests
```

- **Purpose:** Install the Requests library into the existing bind-mounted `.venv` from inside the same Python container image used to create it.
- **Arguments:** `run --rm`: temporary container; `-v "$PWD:/workspace:Z"`: project bind mount with SELinux relabel; `-w /workspace`: working directory; `.venv/bin/python -m pip`: use the environment's pip; `install requests`: install the reviewed Python package from the configured index.
- **Use case:** After creating `.venv` with the previous command, install Requests for NetBox or firewall REST API test scripts. Requires network/package-index access; prefer approved pinned versions and do not expose secrets in the mounted project.
- **Official reference:** https://docs.podman.io/en/latest/markdown/podman-run.1.html

> Not lab-verified.
