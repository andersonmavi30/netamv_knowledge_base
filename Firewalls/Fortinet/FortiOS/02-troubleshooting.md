---
tags: [cli, fortinet, fortios, troubleshooting]
vendor: Fortinet
os: "FortiOS"
validation: not-lab-verified
---

# 🛠️ Troubleshooting

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Fortinet](../README.md)

**Platform:** Fortinet / FortiOS · **Compatibility:** FortiOS 7.x (verify your exact release).

## `execute ping 192.0.2.10`

```text
execute ping 192.0.2.10
```

- **Purpose:** Test ICMP reachability to a host.
- **Arguments:** Replace the documentation IP with your lab target.
- **Use case:** Test reachability before inspecting policy.

- **Practical filter:** `get router info routing-table all | grep 192.0.2` — After ping failure, check the lab prefix.

## `execute traceroute 192.0.2.10`

```text
execute traceroute 192.0.2.10
```

- **Purpose:** Inspect network hops toward a destination.
- **Arguments:** The IP is the destination.
- **Use case:** Look for an unexpected routing path.

- **Practical filter:** `get router info routing-table all | grep 192.0.2` — Check the route after traceroute.

## `diagnose sniffer packet any 'host 192.0.2.10 and tcp port 443' 4 20 l`

```text
diagnose sniffer packet any 'host 192.0.2.10 and tcp port 443' 4 20 l
```

- **Purpose:** Capture matching packets; stop automatically after 20 packets.
- **Arguments:** any: all interfaces; filter: host and TCP port; 4: interface plus packet header; 20: maximum packets; l: local timestamps.
- **Use case:** Confirm ingress and egress interface for TCP/443.
- **Caution:** Packet captures may expose traffic metadata. Limit scope; Ctrl+C stops early.

- **Practical filter:** `diagnose sniffer packet any 'host 192.0.2.10 and tcp port 443' 4 20 l` — Packet filter is already inside the sniffer (BPF), without a pipe.

## `diagnose vpn tunnel list`

```text
diagnose vpn tunnel list
```

- **Purpose:** Inspect IPsec VPN tunnel diagnostic information.
- **Arguments:** No arguments.
- **Use case:** Check established SAs during VPN troubleshooting.

- **Practical filter:** `diagnose vpn tunnel list | grep -i name=` — Find tunnel names; inspect full output for tunnel state.


> **Note:** Quick reference, not lab-verified; confirm syntax and permissions on your model and release.

**Vendor reference:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966
