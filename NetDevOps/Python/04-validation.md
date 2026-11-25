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
