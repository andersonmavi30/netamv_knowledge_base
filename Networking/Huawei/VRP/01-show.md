---
tags: [cli, huawei, vrp, show]
vendor: Huawei
os: "VRP"
versions: "VRP (generic; confirm your device's release)"
validation: not-lab-verified
---

# 🔎 Show and status

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Huawei](../README.md)

**Platform:** Huawei / VRP · **Reference version:** VRP (generic; confirm your device's release).

## `display version`

```text
display version | include VRP
```

- **Purpose:** Show VRP version and uptime.
- **Parameters/filters:** No flags; check model and release.
- **Operational example:** Identify release before a change.

## `display device`

```text
display device | include Normal
```

- **Purpose:** Show hardware and board status.
- **Parameters/filters:** No flags; availability varies by platform.
- **Operational example:** Check hardware before troubleshooting.

## `display interface brief`

```text
display interface brief | include DOWN
```

- **Purpose:** Summarize links and error counters.
- **Parameters/filters:** brief: condensed view.
- **Operational example:** Find down ports.

## `display ip interface brief`

```text
display ip interface brief | include Vlanif
```

- **Purpose:** List IPv4 interfaces and link state.
- **Parameters/filters:** brief: short interface IP table.
- **Operational example:** Confirm management SVI IP.

## `display ip routing-table 198.51.100.10`

```text
display ip routing-table 198.51.100.10
```

- **Purpose:** Query routes for a destination IP.
- **Parameters/filters:** IP: focused destination lookup.
- **Operational example:** Check forwarding to a remote host.

> Verify commands and options with on-device CLI help; examples are not yet lab-validated.

**Vendor references:** [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100333403/cdd85713/basic-interface-configuration-commands) · [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100335692/c1ebaf03/basic-ip-routing-configuration)
