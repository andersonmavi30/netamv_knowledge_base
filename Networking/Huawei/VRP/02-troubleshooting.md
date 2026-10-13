---
tags: [cli, huawei, vrp, troubleshooting]
vendor: Huawei
os: "VRP"
versions: "VRP (generic; confirm your device's release)"
validation: not-lab-verified
---

# 🛠️ Troubleshooting

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Huawei](../README.md)

**Platform:** Huawei / VRP · **Reference version:** VRP (generic; confirm your device's release).

## `ping 192.0.2.10`

```text
ping 192.0.2.10
```

- **Purpose:** Test ICMP reachability.
- **Parameters/filters:** IP: target.
- **Operational example:** Confirm the path to a gateway.

## `tracert 198.51.100.10`

```text
tracert 198.51.100.10
```

- **Purpose:** Trace IPv4 hops to the target.
- **Parameters/filters:** IP: target address.
- **Operational example:** Find where traffic stops.

## `display interface GigabitEthernet0/0/1`

```text
display interface GigabitEthernet0/0/1
```

- **Purpose:** Inspect a port's statistics and errors.
- **Parameters/filters:** Interface ID varies across models.
- **Operational example:** Look for error packets or link flaps.

## `display logbuffer | include DOWN`

```text
display logbuffer | include DOWN
```

- **Purpose:** Find log lines containing DOWN.
- **Parameters/filters:** | include: matching lines only.
- **Operational example:** Find interfaces going down.

## `display arp | include 192.0.2.10`

```text
display arp | include 192.0.2.10
```

- **Purpose:** Find a host's ARP entry.
- **Parameters/filters:** | include: text match, not complete context.
- **Operational example:** Check whether the MAC was learned.

> Verify commands and options with on-device CLI help; examples are not yet lab-validated.

**Vendor references:** [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100333403/cdd85713/basic-interface-configuration-commands) · [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100335692/c1ebaf03/basic-ip-routing-configuration)
