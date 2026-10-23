---
tags: [cli, mikrotik, routeros, troubleshooting]
vendor: MikroTik
os: "RouterOS"
versions: "7.x"
validation: not-lab-verified
---

# 🛠️ Troubleshooting

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ MikroTik](../README.md)

**Platform:** MikroTik / RouterOS · **Reference version:** 7.x.

## `/ping 192.0.2.10 count=5 src-address=192.0.2.1`

```text
/ping 192.0.2.10 count=5 src-address=192.0.2.1
```

- **Purpose:** Ping five times using a chosen source IP.
- **Parameters/filters:** count: packet count; src-address: source IP.
- **Operational example:** Test a route from the LAN address.

## `/tool traceroute 198.51.100.10`

```text
/tool traceroute 198.51.100.10
```

- **Purpose:** Show hops to a host.
- **Parameters/filters:** Destination IP: route target.
- **Operational example:** Locate where forwarding stops.

## `/ip firewall connection print where src-address~"192.0.2.10"`

```text
/ip firewall connection print where src-address~"192.0.2.10"
```

- **Purpose:** Find tracked sessions sourced by a host.
- **Parameters/filters:** where + ~: match IP text, including IP:port.
- **Operational example:** Check an internal host's connections.

## `/log print where message~"error"`

```text
/log print where message~"error"
```

- **Purpose:** Display log entries containing error.
- **Parameters/filters:** message~: case-sensitive text pattern.
- **Operational example:** Search recent fault messages.

## `/tool sniffer quick ip-protocol=icmp`

```text
/tool sniffer quick filter-ip-protocol=icmp
```

- **Purpose:** Watch ICMP packets live.
- **Parameters/filters:** quick: live packet view; ip-protocol: ICMP filter.
- **Operational example:** See whether pings reach the router.
- **Caution:** Packet capture can contain sensitive traffic; stop with Ctrl+C.

> Verify commands and options with on-device CLI help; examples are not yet lab-validated.

**Vendor references:** [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8978498/Console) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/328084/IP+Routing) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8323088/Packet+Sniffer)
