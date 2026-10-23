---
tags: [cli, palo-alto-networks, pan-os, packet-debug]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# 🧪 Packet capture & debug

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ PAN-OS index](README.md)

**Compatibility:** PAN-OS (revisar versión exacta con `show system info | match sw-version`). Commands vary by release, platform, vsys and routing mode.

## Apply capture filter by host and port

```text
debug dataplane packet-diag set filter match source 192.0.2.10 destination 198.51.100.10 destination-port 443 protocol 6
debug dataplane packet-diag set filter on
```

- **Purpose:** Enable a capture filter for a specific TCP flow.
- **Parameters and filters:** source/destination: IPs; destination-port: 443; protocol 6: TCP; on: activate.
- **Operational use:** Investigate HTTPS failures without capturing all traffic.
- **Caution:** Always use authorized lab/test traffic and limit collection.

## Configure bounded receive and drop stages

```text
debug dataplane packet-diag set capture stage receive file pan-rx.pcap packet-count 100
debug dataplane packet-diag set capture stage drop file pan-drop.pcap packet-count 100
```

- **Purpose:** Configure separate receive/drop PCAP files.
- **Parameters and filters:** stage: processing point; file: PCAP name; packet-count: packet limit.
- **Operational use:** Check if packets arrive but get dropped by the firewall.

## Start a short packet capture

```text
debug dataplane packet-diag show setting
debug dataplane packet-diag set capture on
```

- **Purpose:** Review capture settings, then enable packet collection.
- **Parameters and filters:** show setting: review filters/stages; capture on: start.
- **Operational use:** Capture a short test connection from a lab client.
- **Caution:** Packet capture can affect resources; stop immediately after test.

## Stop capture and filters

```text
debug dataplane packet-diag set capture off
debug dataplane packet-diag set filter off
```

- **Purpose:** Stop both capture collection and packet filtering.
- **Parameters and filters:** capture off: stop writing PCAP; filter off: disable filter.
- **Operational use:** Leave troubleshooting state disabled when finished.

## Investigate per-flow dataplane drops

```text
show counter global filter severity drop delta yes
```

- **Purpose:** Review incrementing dataplane drop counters while testing.
- **Parameters and filters:** severity drop: counters categorized as drops; delta yes: incremental changes.
- **Operational use:** Find traffic loss during the captured HTTPS connection.
- **Caution:** Delta must be sampled more than once; use only with scoped testing.

> Illustrative examples pending lab testing. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Docs 1](https://docs.paloaltonetworks.com/ngfw/administration/monitoring/take-packet-captures) · [Docs 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
