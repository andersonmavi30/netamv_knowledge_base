---
tags: [cli, palo-alto-networks, pan-os, troubleshooting]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Troubleshooting

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ PAN-OS index](README.md)

**Platform:** Palo Alto Networks / PAN-OS · **Compatibility:** Verify the installed version with `show system info | match sw-version`. Commands vary by release, platform, vsys and routing mode.

## `show session all filter source 192.0.2.10`

```text
show session all filter source 192.0.2.10
```

- **Purpose:** Find sessions with this source IP using built-in session filters.
- **Arguments:** filter source: filter session table by source IP.
- **Use case:** Confirm if a client creates sessions through the firewall.

## `show session all filter destination 198.51.100.10 destination-port 443`

```text
show session all filter destination 198.51.100.10 destination-port 443
```

- **Purpose:** Focus on connections to a server and destination port.
- **Arguments:** destination: target IP; destination-port: target TCP/UDP port.
- **Use case:** Investigate failed access to an HTTPS application.
- **Caution:** Destination-port alone does not guarantee a TCP-only filter; specify protocol 6 where needed.

## `show counter global filter severity drop delta yes`

```text
show counter global filter severity drop delta yes
```

- **Purpose:** Show drop-class counters since the prior sample.
- **Arguments:** severity drop: drop-related counters; delta yes: values since preceding sample.
- **Use case:** Correlate drops with a connectivity test.
- **Caution:** The first delta sample may not be representative; repeat the command.

## `test security-policy-match from trust to untrust source 192.0.2.10 destination 198.51.100.10 destination-port 443 protocol 6`

```text
test security-policy-match from trust to untrust source 192.0.2.10 destination 198.51.100.10 destination-port 443 protocol 6
```

- **Purpose:** Find the security rule matching the proposed TCP connection.
- **Arguments:** from/to: zones; source/destination: IPs; destination-port: 443; protocol 6: TCP.
- **Use case:** Explain why a client might be blocked by a rule.
- **Caution:** An application-specific policy may require specifying application as well.

## `test nat-policy-match from trust to untrust source 192.0.2.10 destination 198.51.100.10 destination-port 443 protocol 6`

```text
test nat-policy-match from trust to untrust source 192.0.2.10 destination 198.51.100.10 destination-port 443 protocol 6
```

- **Purpose:** Predict the NAT rule matching a candidate flow.
- **Arguments:** from/to: zones; source/destination: addresses; protocol 6: TCP.
- **Use case:** Check which NAT rule a lab HTTPS flow would match.

> Quick reference, not lab-verified. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Official documentation 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy) · [Official documentation 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking)
