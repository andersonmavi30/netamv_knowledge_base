---
tags: [python, netdevops, automation, cli]
validation: not-lab-verified
---

# Virtual environments

[🇬🇧 English](02-virtual-environments.md) · [🇨🇴 Español](02-virtual-environments.es.md) · [↩ Python](README.md)

**Platform:** Python 3.10+; Linux/macOS Bash; Windows activation commands differ.

## `python3 -m venv .venv`

```bash
python3 -m venv .venv
```

- **Purpose:** Create an isolated Python environment in the project's `.venv` directory.
- **Arguments:** `-m venv`: run Python's standard virtual environment module; `.venv`: directory to create. Python must include `venv`.
- **Use case:** Before building a NetBox API integration, create a dedicated project environment to isolate package versions.
- **Official reference:** https://docs.python.org/3/library/venv.html

> Not lab-verified.

## `source .venv/bin/activate`

```bash
source .venv/bin/activate
```

- **Purpose:** Activate the existing virtual environment in the current Bash shell.
- **Arguments:** `source`: execute the activation script in the current shell; `.venv/bin/activate`: activation script created by `venv`. Linux/macOS Bash syntax.
- **Use case:** Activate the environment before installing Python libraries or running automation scripts; Windows PowerShell uses `.venv\Scripts\Activate.ps1`.
- **Official reference:** https://docs.python.org/3/library/venv.html

> Not lab-verified.
