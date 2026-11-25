---
tags: [python, netdevops, automation, cli]
validation: not-lab-verified
---

# Validation and diagnostics

[🇬🇧 English](04-validation.md) · [🇨🇴 Español](04-validation.es.md) · [↩ Python](README.md)

**Platform:** Python 3.10+; use of a virtual environment is recommended.

## `python -m pip check`

```bash
python -m pip check
```

- **Purpose:** Check installed distributions for missing or incompatible declared dependencies.
- **Arguments:** `-m pip`: use the active interpreter; `check`: report dependency conflicts; read-only.
- **Use case:** Detect a dependency mismatch in a network automation project's virtual environment.
- **Official reference:** https://pip.pypa.io/en/stable/cli/pip_check/

> Not lab-verified.

## `python -m json.tool payload.json`

```bash
python -m json.tool payload.json
```

- **Purpose:** Validate JSON syntax and pretty-print an input file to the terminal.
- **Arguments:** `-m json.tool`: run the standard JSON utility; `payload.json`: example input file. Invalid JSON produces an error and nonzero exit status.
- **Use case:** Check a NetBox or firewall REST API request body before using it in an automation script.
- **Official reference:** https://docs.python.org/3/library/json.html#module-json.tool

> Not lab-verified.
