---
tags: [cli, palo-alto-networks, pan-os, packet-debug]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Packet capture & debug

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ PAN-OS index](README.md)

**Platform:** Palo Alto Networks / PAN-OS · **Compatibility:** Verify the installed version with `show system info | match sw-version`. Commands vary by release, platform, vsys and routing mode.

## Apply capture filter by host and port

```text
debug dataplane packet-diag set filter match source 192.0.2.10 destination 198.51.100.10 destination-port 443 protocol 6
debug dataplane packet-diag set filter on
```

- **Purpose:** Enable a capture filter for a specific TCP flow.
- **Arguments:** source/destination: IPs; destination-port: 443; protocol 6: TCP; on: activate.
- **Use case:** Investigate HTTPS failures without capturing all traffic.
- **Caution:** Always use authorized lab/test traffic and limit collection.

## Configure bounded receive and drop stages

```text
debug dataplane packet-diag set capture stage receive file pan-rx.pcap packet-count 100
debug dataplane packet-diag set capture stage drop file pan-drop.pcap packet-count 100
```

- **Purpose:** Configure separate receive/drop PCAP files.
- **Arguments:** stage: processing point; file: PCAP name; packet-count: packet limit.
- **Use case:** Check if packets arrive but get dropped by the firewall.

## Start a short packet capture

```text
debug dataplane packet-diag show setting
debug dataplane packet-diag set capture on
```

- **Purpose:** Review capture settings, then enable packet collection.
- **Arguments:** show setting: review filters/stages; capture on: start.
- **Use case:** Capture a short test connection from a lab client.
- **Caution:** Packet capture can affect resources; stop immediately after test.

## Stop capture and filters

```text
debug dataplane packet-diag set capture off
debug dataplane packet-diag set filter off
```

- **Purpose:** Stop both capture collection and packet filtering.
- **Arguments:** capture off: stop writing PCAP; filter off: disable filter.
- **Use case:** Leave troubleshooting state disabled when finished.

## Investigate per-flow dataplane drops

```text
show counter global filter severity drop delta yes
```

- **Purpose:** Review incrementing dataplane drop counters while testing.
- **Arguments:** severity drop: counters categorized as drops; delta yes: incremental changes.
- **Use case:** Find traffic loss during the captured HTTPS connection.
- **Caution:** Delta must be sampled more than once; use only with scoped testing.

> Quick reference, not lab-verified. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Official documentation 1](https://docs.paloaltonetworks.com/ngfw/administration/monitoring/take-packet-captures) · [Official documentation 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
