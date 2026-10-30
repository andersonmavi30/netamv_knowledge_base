---
tags: [cli, f5, big-ip, tmos, show]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Show & status

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Index](README.md)

**Platform:** F5 BIG-IP / TMOS · **Context:** Bash (tmsh prefix). Version and modules vary; verify using `tmsh show sys version`.

## `tmsh show sys version | grep Version`

```text
tmsh show sys version | grep Version
```

- **Purpose:** Read BIG-IP version only.
- **Arguments:** tmsh: Traffic Management Shell; grep: matching line.
- **Use case:** Verify compatibility before a change.

## `tmsh show cm sync-status`

```text
tmsh show cm sync-status
```

- **Purpose:** Inspect device-group synchronization.
- **Arguments:** cm sync-status: sync state.
- **Use case:** Find an out-of-sync HA device.

## `tmsh list ltm virtual | grep -i lab_vs`

```text
tmsh list ltm virtual | grep -i lab_vs
```

- **Purpose:** Find a virtual server name.
- **Arguments:** list: configuration; grep -i: ignore case.
- **Use case:** Locate a lab VIP config.

## `tmsh show sys performance system | grep -i cpu`

```text
tmsh show sys performance system | grep -i cpu
```

- **Purpose:** Inspect CPU-related system performance.
- **Arguments:** show sys performance: resource summary; grep -i: filter.
- **Use case:** Investigate control-plane load.

> Not lab-verified. Some commands require LTM, HA or Bash privileges; release capabilities differ.

**Official documentation:** [1](https://clouddocs.f5.com/cli/tmsh-reference/v16/general/tmsh.html) · [2](https://clouddocs.f5.com/cli/tmsh-reference/v16/general/grep.html)
