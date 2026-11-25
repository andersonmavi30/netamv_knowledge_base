---
tags: [python, netdevops, automation, cli]
validation: not-lab-verified
---

# pip and project dependencies

[🇬🇧 English](03-packages.md) · [🇨🇴 Español](03-packages.es.md) · [↩ Python](README.md)

**Platform:** Python 3.10+; Linux/macOS Bash; Windows activation commands differ.

## `python -m pip install requests`

```bash
python -m pip install requests
```

- **Purpose:** Install the `requests` HTTP client into the active Python environment for REST API automation.
- **Arguments:** `-m pip`: execute pip with the active Python interpreter; `install`: download/install a package; `requests`: package name. Requires package-index access.
- **Use case:** Install Requests inside `.venv` to query a lab NetBox or firewall REST API; review and pin approved versions for reproducibility.
- **Official reference:** https://pip.pypa.io/en/stable/cli/pip_install/

> Not lab-verified.

## `python -m pip install netmiko`

```bash
python -m pip install netmiko
```

- **Purpose:** Install Netmiko for SSH-based network device automation into the active Python environment.
- **Arguments:** `-m pip`: run pip with the current interpreter; `install`: install from the configured package index; `netmiko`: package name.
- **Use case:** Inside an activated `.venv`, install Netmiko for a controlled lab script that reads switch interface status via SSH.
- **Official reference:** https://pip.pypa.io/en/stable/cli/pip_install/

> Not lab-verified.
