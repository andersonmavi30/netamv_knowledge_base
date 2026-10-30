---
tags: [cli, f5, big-ip, tmos, field-commands]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Additional operational checks

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Index](README.md)

**Platform:** F5 BIG-IP / TMOS · **Context:** Bash (tmsh prefix). Version and modules vary; verify using `tmsh show sys version`.

## `tmsh list sys ntp`

```text
tmsh list sys ntp
```

- **Purpose:** Inspect configured NTP peers.
- **Arguments:** sys ntp: NTP configuration.
- **Use case:** Check event-time accuracy.

## `tmsh list sys dns`

```text
tmsh list sys dns
```

- **Purpose:** Inspect device DNS resolvers.
- **Arguments:** sys dns: management DNS.
- **Use case:** Troubleshoot FQDN health monitor issues.

## `tmsh show sys version detail | grep -i hotfix`

```text
tmsh show sys version detail | grep -i hotfix
```

- **Purpose:** Find hotfix details for change planning.
- **Arguments:** detail: extended release; grep -i: filter.
- **Use case:** Check release after patch.

## `tmsh list ltm monitor http | grep -i lab`

```text
tmsh list ltm monitor http | grep -i lab
```

- **Purpose:** Find custom HTTP monitors.
- **Arguments:** list: monitor config; grep -i: name match.
- **Use case:** Audit app health-check names.

> Not lab-verified. Some commands require LTM, HA or Bash privileges; release capabilities differ.

**Official documentation:** [1](https://clouddocs.f5.com/cli/tmsh-reference/v16/general/tmsh.html)
