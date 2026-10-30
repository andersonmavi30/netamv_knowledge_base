---
tags: [cli, f5, big-ip, tmos, packet-debug]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Packet capture & diagnostics

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Index](README.md)

**Platform:** F5 BIG-IP / TMOS · **Context:** Bash / Advanced Shell. Version and modules vary; verify using `tmsh show sys version`.

## `tcpdump -nni 0.0:nnn -s0 -c 25 'host 192.0.2.10 and tcp port 443'`

```text
tcpdump -nni 0.0:nnn -s0 -c 25 'host 192.0.2.10 and tcp port 443'
```

- **Purpose:** Capture up to 25 packets on TMM.
- **Arguments:** -nn: numeric ports/IPs; -i: interface; -s0: full packet; -c: limit.
- **Use case:** Trace an HTTPS client.
- **Caution:** May show sensitive payload; 0.0:nnn not appropriate on every hardware role.

## `tcpdump -nni 0.0:nnn -s0 -c 50 -w /var/tmp/lab-https.pcap 'host 198.51.100.10 and port 443'`

```text
tcpdump -nni 0.0:nnn -s0 -c 50 -w /var/tmp/lab-https.pcap 'host 198.51.100.10 and port 443'
```

- **Purpose:** Save filtered packets to PCAP.
- **Arguments:** -w: output file; -c: count; BPF: VIP/port.
- **Use case:** Open in Wireshark for analysis.
- **Caution:** Restrict file access and delete after review.

## `tcpdump -nni 0.0:nnn -c 20 'arp or icmp'`

```text
tcpdump -nni 0.0:nnn -c 20 'arp or icmp'
```

- **Purpose:** Inspect ARP and ICMP in TMM.
- **Arguments:** -c 20: bounded capture; BPF: arp or icmp.
- **Use case:** Investigate a gateway connectivity issue.

## `tmsh show sys connection cs-server-addr 192.0.2.20`

```text
tmsh show sys connection cs-server-addr 192.0.2.20
```

- **Purpose:** Inspect connections sent to a backend.
- **Arguments:** cs-server-addr: server-side IP match, if supported.
- **Use case:** Compare connections against the packet capture.
- **Caution:** Confirm syntax with tmsh help for installed version.

> Not lab-verified. Some commands require LTM, HA or Bash privileges; release capabilities differ.

**Official documentation:** [1](https://my.f5.com/manage/s/article/K000132760) · [2](https://clouddocs.f5.com/cli/tmsh-reference/v16/general/tmsh.html)
