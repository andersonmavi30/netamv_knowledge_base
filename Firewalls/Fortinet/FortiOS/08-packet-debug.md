---
tags: [cli, packet-capture, debugging]
validation: not-lab-verified
---

# 🧪 Packet capture & debugging — Fortinet FortiOS

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Index](README.md)

**Reference version:** FortiOS 7.x.

> ⚠️ Captures and debugging may consume resources or expose sensitive data. Use only on authorized networks, scope carefully and always stop afterward.

## diagnose sniffer packet any 'host 192.0.2.10 and tcp port 443' 4 20 a

```text
diagnose sniffer packet any 'host 192.0.2.10 and tcp port 443' 4 20 a
```

- **Purpose:** Capture up to 20 TCP/443 packets for a host, including interface names.
- **Parameters:** any: all interfaces; BPF: host/port; 4: packet header + interface; 20: limit; a: absolute time.
- **Real-world use:** Identify inbound/outbound interfaces for a failed HTTPS connection.

## diagnose sniffer packet any 'arp or icmp' 4 20 a

```text
diagnose sniffer packet any 'arp or icmp' 4 20 a
```

- **Purpose:** Inspect ARP resolution and ICMP with a bounded capture.
- **Parameters:** arp or icmp: BPF alternatives; 20: packet limit.
- **Real-world use:** Determine whether ARP and ping packets reach the firewall.

## diagnose debug disable

```text
diagnose debug disable
diagnose debug reset
```

- **Purpose:** Stop active debugging and reset previous debug filters.
- **Parameters:** disable: stop debug; reset: clear debug settings.
- **Real-world use:** Leave the firewall clean after troubleshooting.

**Vendor reference:** https://docs.fortinet.com/document/fortigate/7.4.0/administration-guide/680228/performing-a-sniffer-trace-cli-and-packet-capture

**Note:** EPC/sniffer may not see hardware-offloaded packets. Protocol debugging is not the same as PCAP.

## `diagnose sniffer packet any 'src host 192.0.2.10 and dst host 198.51.100.20' 4 20 a`

```text
diagnose sniffer packet any 'src host 192.0.2.10 and dst host 198.51.100.20' 4 20 a
```

- **Purpose:** Capture up to 20 packets between designated source and destination.
- **Arguments:** `any`: all interfaces; `src/dst host`: directional BPF filter; `4`: interface/header; `20`: limit; `a`: absolute timestamps.
- **Use case:** Find whether a test flow enters and leaves the firewall.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.8/administration-guide/680228/performing-a-sniffer-trace-or-packet-capture

> Not lab-verified. Use only for authorized troubleshooting.

## `diagnose sniffer packet port1 'src host 192.0.2.10 and icmp' 4 20 a`

```text
diagnose sniffer packet port1 'src host 192.0.2.10 and icmp' 4 20 a
```

- **Purpose:** Capture a bounded ICMP trace from a source on port1.
- **Arguments:** `port1`: example interface; `src host`: source filter; `icmp`: protocol; `4 20 a`: verbosity, count, timestamp.
- **Use case:** Isolate whether ICMP reaches the expected internal port.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.8/administration-guide/680228/performing-a-sniffer-trace-or-packet-capture

> Not lab-verified. Use only for authorized troubleshooting.

## `diagnose debug flow trace stop`

```text
diagnose debug flow trace stop
```

- **Purpose:** Stop any active packet flow tracing session.
- **Arguments:** `flow trace stop`: stop ongoing flow trace; use `diagnose debug reset` for complete cleanup.
- **Use case:** End flow diagnostics after collecting sufficient evidence.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Not lab-verified. Use only for authorized troubleshooting.
