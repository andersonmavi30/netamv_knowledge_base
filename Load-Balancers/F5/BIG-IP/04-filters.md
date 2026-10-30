---
tags: [cli, f5, big-ip, tmos, filters]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Output filters

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Index](README.md)

**Platform:** F5 BIG-IP / TMOS · **Context:** Bash (tmsh prefix). Version and modules vary; verify using `tmsh show sys version`.

## `tmsh list ltm virtual | grep -i lab`

```text
tmsh list ltm virtual | grep -i lab
```

- **Purpose:** Search virtual server configurations by name.
- **Arguments:** | grep -i: case-insensitive string search.
- **Use case:** Find app VIPs quickly.

## `tmsh show ltm pool | grep -i offline`

```text
tmsh show ltm pool | grep -i offline
```

- **Purpose:** Look for offline pool lines.
- **Arguments:** grep -i: match case-insensitively.
- **Use case:** Locate affected pools.
- **Caution:** Read the full pool object for exact member state.

## `tmsh list ltm pool /Common/lab_pool | grep -A 8 members`

```text
tmsh list ltm pool /Common/lab_pool | grep -A 8 members
```

- **Purpose:** Show member configuration with context.
- **Arguments:** -A 8: eight lines after the matching line.
- **Use case:** Review a backend list.

## `tmsh list ltm virtual | grep -i destination`

```text
tmsh list ltm virtual | grep -i destination
```

- **Purpose:** Show configured virtual destinations.
- **Arguments:** grep -i destination: field match.
- **Use case:** Find VIP IPs/ports.

> Not lab-verified. Some commands require LTM, HA or Bash privileges; release capabilities differ.

**Official documentation:** [1](https://clouddocs.f5.com/cli/tmsh-reference/v16/general/grep.html)
