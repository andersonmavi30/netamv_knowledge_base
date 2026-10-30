---
tags: [cli, f5, big-ip, tmos, operations]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# LTM operations

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ Index](README.md)

**Platform:** F5 BIG-IP / TMOS · **Context:** Bash (tmsh prefix). Version and modules vary; verify using `tmsh show sys version`.

## `tmsh show ltm pool /Common/lab_pool members`

```text
tmsh show ltm pool /Common/lab_pool members
```

- **Purpose:** Inspect live status of all members.
- **Arguments:** members: per-member status.
- **Use case:** Find offline backend.

## `tmsh show ltm virtual /Common/lab_vs detail`

```text
tmsh show ltm virtual /Common/lab_vs detail
```

- **Purpose:** View VIP counters in detail.
- **Arguments:** detail: expanded statistics.
- **Use case:** Investigate VIP request rate.

## `tmsh list ltm virtual /Common/lab_vs profiles`

```text
tmsh list ltm virtual /Common/lab_vs profiles
```

- **Purpose:** Inspect assigned TCP/HTTP/SSL profiles.
- **Arguments:** profiles: attached profile collection.
- **Use case:** Verify required profile presence.

## `tmsh show cm traffic-group`

```text
tmsh show cm traffic-group
```

- **Purpose:** Inspect failover traffic-group state.
- **Arguments:** cm traffic-group: floating groups.
- **Use case:** Validate HA role before maintenance.

> Not lab-verified. Some commands require LTM, HA or Bash privileges; release capabilities differ.

**Official documentation:** [1](https://clouddocs.f5.com/cli/tmsh-reference/latest/modules/ltm/ltm_virtual.html)
