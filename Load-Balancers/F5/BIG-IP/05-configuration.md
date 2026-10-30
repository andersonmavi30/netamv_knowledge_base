---
tags: [cli, f5, big-ip, tmos, configuration]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Configuration

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Index](README.md)

**Platform:** F5 BIG-IP / TMOS · **Context:** Bash (tmsh prefix). Version and modules vary; verify using `tmsh show sys version`.

## `tmsh create ltm pool /Common/lab_pool members add { 192.0.2.20:80 192.0.2.21:80 } monitor http`

```text
tmsh create ltm pool /Common/lab_pool members add { 192.0.2.20:80 192.0.2.21:80 } monitor http
```

- **Purpose:** Create a test pool with HTTP health monitoring.
- **Arguments:** members add: servers; monitor http: health-check.
- **Use case:** Prepare two HTTP backends.
- **Caution:** Test network reachability and health monitor response before use.

## `tmsh create ltm virtual /Common/lab_vs destination 198.51.100.10:80 pool /Common/lab_pool ip-protocol tcp source-address-translation { type automap }`

```text
tmsh create ltm virtual /Common/lab_vs destination 198.51.100.10:80 pool /Common/lab_pool ip-protocol tcp source-address-translation { type automap }
```

- **Purpose:** Create a lab HTTP virtual server.
- **Arguments:** destination: VIP:port; pool: backend; automap: SNAT.
- **Use case:** Publish lab HTTP service.
- **Caution:** Creation affects traffic immediately; use only approved test space.

## `tmsh list ltm virtual /Common/lab_vs`

```text
tmsh list ltm virtual /Common/lab_vs
```

- **Purpose:** Inspect virtual server after creation.
- **Arguments:** list: object configuration.
- **Use case:** Review destination and pool before save.

## `tmsh save sys config`

```text
tmsh save sys config
```

- **Purpose:** Persist approved BIG-IP configuration.
- **Arguments:** save: persist running config.
- **Use case:** Keep lab settings across reboot.

> Not lab-verified. Some commands require LTM, HA or Bash privileges; release capabilities differ.

**Official documentation:** [1](https://clouddocs.f5.com/training/community/f5cert/html/class8/module01/lab1.html)
