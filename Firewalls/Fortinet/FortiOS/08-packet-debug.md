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

## `diagnose debug flow show function-name enable`

```text
diagnose debug flow show function-name enable
```

- **Purpose:** Include internal function names in flow diagnostic messages.
- **Arguments:** `show function-name enable`: add function-name detail to trace output.
- **Use case:** Find the step where a packet is dropped.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Not lab-verified; stop using `diagnose debug disable`, `diagnose debug flow trace stop`, and `diagnose debug reset`.

## `diagnose debug flow show iprope enable`

```text
diagnose debug flow show iprope enable
```

- **Purpose:** Include firewall policy processing details in flow diagnostics when supported.
- **Arguments:** `show iprope enable`: detailed policy-engine debug output; availability varies.
- **Use case:** Inspect policy matching during a controlled flow trace.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Not lab-verified; stop using `diagnose debug disable`, `diagnose debug flow trace stop`, and `diagnose debug reset`.

## `diagnose debug enable`

```text
diagnose debug enable
```

- **Purpose:** Enable diagnostic output previously configured with filters and trace settings.
- **Arguments:** `debug enable`: starts printing debug output; stop later using disable and reset.
- **Use case:** Begin bounded policy-flow diagnosis after configuring trace count.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Not lab-verified; stop using `diagnose debug disable`, `diagnose debug flow trace stop`, and `diagnose debug reset`.

## `diagnose debug flow filter proto 6`

```text
diagnose debug flow filter proto 6
```

- **Purpose:** Restrict IPv4 flow tracing to TCP traffic (IP protocol number 6).
- **Arguments:** `flow filter`: IPv4 flow-filter settings; `proto 6`: TCP protocol number. Configure a host filter and bounded trace before enabling debug.
- **Use case:** Diagnose TCP connection denial while excluding UDP and ICMP from flow output.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Not lab-verified. Scope IP/protocol/trace count before starting; afterwards run `diagnose debug disable`, `diagnose debug flow trace stop`, and `diagnose debug reset`.

## `diagnose debug flow filter dport 443`

```text
diagnose debug flow filter dport 443
```

- **Purpose:** Restrict IPv4 flow tracing to destination TCP/UDP port 443; combine with `proto 6` for HTTPS over TCP.
- **Arguments:** `dport 443`: destination port 443; the filter is not inherently TCP-only; narrow source/destination IP as well.
- **Use case:** Trace a failed HTTPS/TCP connection to a lab server without dumping unrelated ports.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Not lab-verified. Scope IP/protocol/trace count before starting; afterwards run `diagnose debug disable`, `diagnose debug flow trace stop`, and `diagnose debug reset`.

## `diagnose debug flow filter sport 12345`

```text
diagnose debug flow filter sport 12345
```

- **Purpose:** Restrict flow tracing to packets with an example source port of 12345.
- **Arguments:** `sport 12345`: source transport-layer port; replace with the observed client source port; combine with address/protocol filters.
- **Use case:** Follow one client connection with a known ephemeral source port while diagnosing policy selection.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Not lab-verified. Scope IP/protocol/trace count before starting; afterwards run `diagnose debug disable`, `diagnose debug flow trace stop`, and `diagnose debug reset`.

## `diagnose debug flow filter vd -1`

```text
diagnose debug flow filter vd -1
```

- **Purpose:** Set the IPv4 flow-debug VDOM filter to match all VDOM IDs, where supported.
- **Arguments:** `vd -1`: match all virtual domains; `-1` broadens rather than narrows the scope; apply IP/port filters and a limited trace count.
- **Use case:** Compare policy-flow decisions across multiple VDOMs during a controlled inter-VDOM routing investigation.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Not lab-verified. Use only during authorized, scoped diagnostics; finish with `diagnose debug disable`, `diagnose debug flow trace stop`, `diagnose debug reset`.

## `diagnose debug flow filter6 addr 2001:db8::10`

```text
diagnose debug flow filter6 addr 2001:db8::10
```

- **Purpose:** Restrict IPv6 flow debugging to a documentation-range IPv6 host address.
- **Arguments:** `filter6`: IPv6 flow filters; `addr`: match host IPv6 address; `2001:db8::10`: replace with a real authorized target.
- **Use case:** Diagnose a policy or route mismatch for IPv6 traffic without collecting all IPv6 flows.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Not lab-verified. Use only during authorized, scoped diagnostics; finish with `diagnose debug disable`, `diagnose debug flow trace stop`, `diagnose debug reset`.

## `diagnose debug application ike -1`

```text
diagnose debug application ike -1
```

- **Purpose:** Set verbose diagnostic output for the IKE daemon when investigating IPsec VPN negotiation.
- **Arguments:** `application ike`: IKE daemon; `-1`: verbose debug level. Requires `diagnose debug enable` to display output; scope IKE logging where supported.
- **Use case:** Inspect failed Phase 1/Phase 2 VPN negotiation in a short authorized maintenance window.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.0.0/secgw-for-mobile-networks-deployment/945456

> Not lab-verified. Use only during authorized, scoped diagnostics; finish with `diagnose debug disable`, `diagnose debug reset`.

## `diagnose debug application dnsproxy -1`

```text
diagnose debug application dnsproxy -1
```

- **Purpose:** Set detailed DNS proxy daemon debugging to investigate FortiGate DNS-proxy or DNS-filter behavior.
- **Arguments:** `application dnsproxy`: DNS proxy service; `-1`: verbose debug level; `diagnose debug enable` is also required to emit messages.
- **Use case:** Troubleshoot DNS Filter categorization or DNS proxy failures for a bounded test on an authorized client.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.6/administration-guide/150448/troubleshooting-for-dns-filter

> Not lab-verified. Enable output only for authorized diagnostics using `diagnose debug enable`; then stop with `diagnose debug disable` and `diagnose debug reset`. Review and protect possibly sensitive output.

## `diagnose debug application fnbamd -1`

```text
diagnose debug application fnbamd -1
```

- **Purpose:** Set detailed debug for the authentication daemon used in remote-user authentication.
- **Arguments:** `application fnbamd`: remote authentication daemon; `-1`: verbose level; output begins after `diagnose debug enable`.
- **Use case:** Investigate a RADIUS/LDAP authentication failure during authorized VPN or captive-portal testing; logs may contain sensitive identifiers.
- **Official reference:** https://docs.fortinet.com/document/fortigate/latest/administration-guide/502390/debug-commands

> Not lab-verified. Enable output only for authorized diagnostics using `diagnose debug enable`; then stop with `diagnose debug disable` and `diagnose debug reset`. Review and protect possibly sensitive output.

## `diagnose debug application update -1`

```text
diagnose debug application update -1
```

- **Purpose:** Set detailed logging for the FortiGuard update daemon during update/connectivity troubleshooting.
- **Arguments:** `application update`: FortiGuard update service; `-1`: verbose level; combine with `diagnose debug enable` for output.
- **Use case:** Investigate why a lab FortiGate cannot download AV/IPS/FortiGuard package updates; limit output and protect token-bearing logs.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966/cli-troubleshooting-cheat-sheet

> Not lab-verified. Enable output only for authorized diagnostics using `diagnose debug enable`; then stop with `diagnose debug disable` and `diagnose debug reset`. Review and protect possibly sensitive output.

## `diagnose debug application miglogd 0x1000`

```text
diagnose debug application miglogd 0x1000
```

- **Purpose:** Set a targeted debug level on the log daemon to inspect log-search filter strings, where supported.
- **Arguments:** `application miglogd`: logging daemon; `0x1000`: documented diagnostic bitmask for log-search filters; requires debug output enabled.
- **Use case:** Investigate log-search filtering during FortiAnalyzer/log troubleshooting without enabling an unrestricted general log debug.
- **Official reference:** https://docs.fortinet.com/document/fortigate/7.4.1/administration-guide/668197

> Not lab-verified. Enable output only for authorized diagnostics using `diagnose debug enable`; then stop with `diagnose debug disable` and `diagnose debug reset`. Review and protect possibly sensitive output.
