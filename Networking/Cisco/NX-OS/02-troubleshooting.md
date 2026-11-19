---
tags: [cli, cisco, nx-os]
vendor: Cisco
os: NX-OS
validation: not-lab-verified
---

# Logs and troubleshooting

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ NX-OS](README.md)

**Platform:** Cisco Nexus NX-OS (Nexus 9000 / 10.x); verify syntax by model and release.

## `show logging last 50`

```text
show logging last 50
```

- **Purpose:** Display the 50 most recent buffered syslog messages where the NX-OS release supports this option.
- **Arguments:** `logging`: inspect system messages; `last 50`: restrict output to the latest 50 entries.
- **Use case:** Correlate an interface flap or vPC event with system log messages.
- **Official reference:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Not lab-verified; verify options on your release.
