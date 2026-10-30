---
tags: [cli, f5, big-ip, tmos, troubleshooting]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Troubleshooting

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Index](README.md)

**Platform:** F5 BIG-IP / TMOS · **Context:** Bash (tmsh prefix). Version and modules vary; verify using `tmsh show sys version`.

## `tmsh show ltm virtual /Common/lab_vs`

```text
tmsh show ltm virtual /Common/lab_vs
```

- **Purpose:** Inspect status/reason and traffic of one VIP.
- **Arguments:** /Common/lab_vs: full object path.
- **Use case:** Determine why a VIP is offline.

## `tmsh show ltm pool /Common/lab_pool`

```text
tmsh show ltm pool /Common/lab_pool
```

- **Purpose:** Inspect health of one backend pool.
- **Arguments:** /Common/lab_pool: named pool.
- **Use case:** Locate pool without healthy members.

## `tmsh show sys connection cs-client-addr 192.0.2.10`

```text
tmsh show sys connection cs-client-addr 192.0.2.10
```

- **Purpose:** Find active connections from one client.
- **Arguments:** cs-client-addr: client-side IP filter.
- **Use case:** Confirm requests reach TMM.

## `tmsh show ltm node /Common/192.0.2.20`

```text
tmsh show ltm node /Common/192.0.2.20
```

- **Purpose:** Inspect an individual backend node.
- **Arguments:** node name: example address.
- **Use case:** Investigate a failed backend.

> Not lab-verified. Some commands require LTM, HA or Bash privileges; release capabilities differ.

**Official documentation:** [1](https://clouddocs.f5.com/cli/tmsh-reference/v16/modules/ltm/ltm_pool.html) · [2](https://clouddocs.f5.com/cli/tmsh-reference/latest/modules/ltm/ltm_virtual.html)
