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

## `diagnose debug flow filter clear`

```text
diagnose debug flow filter clear
```

- **Purpose:** Clear previously configured flow address/port filters.
- **Arguments:** `flow filter clear`: remove IPv4 flow filters.
- **Use case:** Prepare a clean diagnostic context.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Not lab-verified; stop and reset debugging after use.

## `diagnose debug flow filter addr 192.0.2.10`

```text
diagnose debug flow filter addr 192.0.2.10
```

- **Purpose:** Trace traffic involving a specific host address.
- **Arguments:** `addr`: match host address; `192.0.2.10`: lab IP.
- **Use case:** Reduce logs to a single test host.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Not lab-verified; stop and reset debugging after use.

## `diagnose debug flow filter saddr 192.0.2.10`

```text
diagnose debug flow filter saddr 192.0.2.10
```

- **Purpose:** Match packets sourced from a particular IPv4 address.
- **Arguments:** `saddr`: IPv4 source filter.
- **Use case:** Trace traffic leaving a workstation.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Not lab-verified; stop and reset debugging after use.

## `diagnose debug flow filter daddr 198.51.100.20`

```text
diagnose debug flow filter daddr 198.51.100.20
```

- **Purpose:** Match packets destined for a particular IPv4 address.
- **Arguments:** `daddr`: IPv4 destination filter.
- **Use case:** Check policies for a server destination.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Not lab-verified; stop and reset debugging after use.

## `diagnose debug flow trace start 20`

```text
diagnose debug flow trace start 20
```

- **Purpose:** Start tracing up to 20 matched flow records.
- **Arguments:** `trace start 20`: start bounded flow trace; configure filters first.
- **Use case:** Review policy and route decisions for a test session.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Not lab-verified; stop using `diagnose debug disable`, `diagnose debug flow trace stop`, and `diagnose debug reset`.
