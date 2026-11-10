---
tags: [cli, juniper, junos]
validation: not-lab-verified
---

# Output filters

[English](04-filters.md) · [Español](04-filters.es.md) · [Index](README.md)

**Compatibility:** Junos OS; verify model, release and `?`.

## `show log messages | match "error"`

```text
show log messages | match "error"
```

- **Purpose:** Filter the system log to lines mentioning error.
- **Arguments:** match: Junos output regular-expression filter; "error": search text, case-sensitive.
- **Use case:** Find matching system errors while troubleshooting.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/filtering-operational-command.html

> Not lab-verified.
