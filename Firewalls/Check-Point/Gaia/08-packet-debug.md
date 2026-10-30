---
tags: [cli, check-point, gaia, packet-debug]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Packet capture & debugging

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Index](README.md)

**Platform:** Check Point / Gaia + Security Gateway · **Context:** Expert. Confirm installed R8x release and appliance role.

## `tcpdump -ni eth1 -c 20 'host 192.0.2.10 and tcp port 443'`

```text
tcpdump -ni eth1 -c 20 'host 192.0.2.10 and tcp port 443'
```

- **Purpose:** Capture 20 HTTPS packets on eth1.
- **Arguments:** -n: numeric addresses; -i: interface; -c 20: packet limit; BPF: host/port.
- **Use case:** Check whether TLS packets arrive.
- **Caution:** Captures can expose sensitive data.

## `fw monitor -F "192.0.2.10,0,198.51.100.20,443,6" -ci 20 -co 20 -o /var/log/lab_fw.cap`

```text
fw monitor -F "192.0.2.10,0,198.51.100.20,443,6" -ci 20 -co 20 -o /var/log/lab_fw.cap
```

- **Purpose:** Capture one TCP flow through firewall inspection points.
- **Arguments:** -F: src IP/port,dst IP/port,protocol; -ci/-co: packet limits; -o: output.
- **Use case:** Determine where a flow stops inside the gateway.
- **Caution:** Use scoped, short captures and remove files after review.

## `fw ctl zdebug + drop | grep 192.0.2.10`

```text
fw ctl zdebug + drop | grep 192.0.2.10
```

- **Purpose:** Observe drop debug messages for a test client.
- **Arguments:** zdebug + drop: kernel drop debug; grep: client IP.
- **Use case:** Find a reason for packet rejection.
- **Caution:** High load risk; stop using Ctrl+C promptly.

## `tcpdump -ni eth1 -c 30 'udp port 500 or udp port 4500'`

```text
tcpdump -ni eth1 -c 30 'udp port 500 or udp port 4500'
```

- **Purpose:** Capture IKE and NAT-T packets.
- **Arguments:** -c 30: limit; UDP 500/4500: IKE/NAT-T.
- **Use case:** Confirm VPN negotiation traverses WAN.

> Reference commands pending lab testing. Verify privileges, Clish/Expert context and release.

**Documentation:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_CLI_ReferenceGuide/Content/Topics-CLIG/FWG/fw-monitor.htm) · [2](https://sc1.checkpoint.com/documents/SD-WAN-with-Smart1/Content/Topics-SD-WAN/13_Troubleshooting.htm)
