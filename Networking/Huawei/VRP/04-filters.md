---
tags: [cli, huawei, vrp, filters]
vendor: Huawei
os: "VRP"
versions: "S-series VRP V200 (platform/release specific)"
validation: not-lab-verified
---

# 🔍 Operational filters

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Huawei](../README.md)

**Platform:** Huawei / VRP · **Reference version:** S-series VRP V200 (platform/release specific).

## `display current-configuration | include sysname`

```text
display current-configuration | include sysname
```

- **Purpose:** Find the configured hostname.
- **Parameters/filters:** | include: keep matching lines.
- **Operational example:** Identify the machine without full config.

## `display interface brief | include GigabitEthernet0/0/1`

```text
display interface brief | include GigabitEthernet0/0/1
```

- **Purpose:** Inspect one port, not the whole list.
- **Parameters/filters:** include: show matches.
- **Operational example:** Check a specific port's status.

## `display logbuffer | include ERROR`

```text
display logbuffer | include ERROR
```

- **Purpose:** Search for ERROR messages.
- **Parameters/filters:** Pipe filtering may vary by software release.
- **Operational example:** Reduce noisy logs.

## `display current-configuration | begin interface`

```text
display current-configuration | begin interface
```

- **Purpose:** Start output at the first interface line.
- **Parameters/filters:** begin: show matching line and everything after.
- **Operational example:** Skip global config lines.

## `display current-configuration | exclude description`

```text
display current-configuration | exclude description
```

- **Purpose:** Hide description lines (not whole blocks).
- **Parameters/filters:** exclude: remove matching lines.
- **Operational example:** Focus on other configuration values.

> Verify commands and options with on-device CLI help; examples are not yet lab-validated.

**Vendor references:** [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100333403/cdd85713/basic-interface-configuration-commands) · [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100335692/c1ebaf03/basic-ip-routing-configuration)
