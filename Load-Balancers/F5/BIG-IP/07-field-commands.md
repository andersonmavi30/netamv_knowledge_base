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

## `tmsh show ltm persistence persist-records | grep 192.0.2.10`

```text
tmsh show ltm persistence persist-records | grep 192.0.2.10
```

- **Purpose:** Search LTM persistence records for a specific client IP.
- **Arguments:** show ltm persistence persist-records: active persistence bindings; | grep: select the client's matching lines.
- **Use case:** Investigate why a client keeps returning to the same backend even after load-balancing changes.
- **Official reference:** https://clouddocs.f5.com/training/community/adc/html/class7/modules/module02.html

## `tmsh list ltm virtual-address | grep 198.51.100.10`

```text
tmsh list ltm virtual-address | grep 198.51.100.10
```

- **Purpose:** Locate the virtual-address configuration matching one VIP address.
- **Arguments:** list ltm virtual-address: virtual IP configuration; | grep: match the desired VIP.
- **Use case:** Confirm whether a VIP address exists before investigating its virtual server.
- **Reference:** https://clouddocs.f5.com/cli/tmsh-reference/v15/modules/ltm/ltm_virtual-address.html

> Not lab-verified. Some commands require LTM, HA or Bash privileges; release capabilities differ.

**Official documentation:** [1](https://clouddocs.f5.com/cli/tmsh-reference/v16/general/tmsh.html)
