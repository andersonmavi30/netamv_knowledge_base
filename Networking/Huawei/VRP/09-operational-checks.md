---
tags: [cli, networking, operational-checks]
validation: not-lab-verified
---

# Additional operational checks — Huawei VRP

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Index](README.md)

**Compatibility:** VRP generic (verify platform/release). Confirm commands and options with the installed CLI help.

## Interface error counters

```text
display interface counters errors | include GigabitEthernet
```

- **Purpose:** Check error counters across interfaces.
- **Parameters / flags:** counters errors: aggregate error view, if supported.
- **Operational use:** Detect a damaged uplink.
- **Filter / verification:** `display interface counters errors`

## OSPF neighbors overview

```text
display ospf peer brief | include Init
```

- **Purpose:** List OSPF peers in compact form.
- **Parameters / flags:** brief: shortened peer table.
- **Operational use:** Find a neighbor not Full.
- **Filter / verification:** `display ospf peer brief | include Init`

## Static route table

```text
display ip routing-table protocol static | include 198.51.100
```

- **Purpose:** Display only static routes.
- **Parameters / flags:** protocol static: route-source filter.
- **Operational use:** Verify a provisioned static route.
- **Filter / verification:** `display ip routing-table protocol static | include 198.51.100`

## System time verification

```text
display clock
```

- **Purpose:** Show date, time and time-zone status.
- **Parameters / flags:** No flags.
- **Operational use:** Correlate alarms with firewall logs.
- **Filter / verification:** `display clock`

## CPU utilization check

```text
display cpu-usage
```

- **Purpose:** Check CPU usage where the command is supported.
- **Parameters / flags:** CPU stats vary by model and board.
- **Operational use:** Investigate slow management CLI.
- **Filter / verification:** `display cpu-usage`

> ⚠️ Not lab-tested; different Dell and Huawei platforms may use alternative commands.

[Vendor reference](https://info.support.huawei.com/enterprise/en/doc/EDOC1100333403/cdd85713/basic-interface-configuration-commands)
