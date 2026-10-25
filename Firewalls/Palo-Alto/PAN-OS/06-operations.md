---
tags: [cli, palo-alto-networks, pan-os, operations]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# VPN, policy & operational checks

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ PAN-OS index](README.md)

**Platform:** Palo Alto Networks / PAN-OS · **Compatibility:** Verify the installed version with `show system info | match sw-version`. Commands vary by release, platform, vsys and routing mode.

## `show vpn ike-sa gateway LAB-IKE`

```text
show vpn ike-sa gateway LAB-IKE
```

- **Purpose:** Find Phase 1 SAs by gateway name.
- **Arguments:** gateway: configured IKE gateway name.
- **Use case:** Investigate phase 1 negotiation failure.

## `show vpn ipsec-sa tunnel LAB-IPSEC`

```text
show vpn ipsec-sa tunnel LAB-IPSEC
```

- **Purpose:** Find Phase 2 SAs for a named tunnel.
- **Arguments:** tunnel: selected IPsec tunnel.
- **Use case:** Determine whether phase 2 is installed.

## `show vpn flow name LAB-IPSEC`

```text
show vpn flow name LAB-IPSEC
```

- **Purpose:** Inspect packets and tunnel flow status for one IPsec tunnel.
- **Arguments:** name: tunnel name.
- **Use case:** Check if encrypted tunnel counters change with test traffic.

## `show running security-policy | match LAB-ALLOW-HTTPS`

```text
show running security-policy | match LAB-ALLOW-HTTPS
```

- **Purpose:** Search installed security policy output by name.
- **Arguments:** match: exact text matching on output lines.
- **Use case:** Verify intended policy is in the running rulebase.

## `show running rule-use hit-count vsys vsys1 rule-base security rules rule-name LAB-ALLOW-HTTPS`

```text
show running rule-use hit-count vsys vsys1 rule-base security rules rule-name LAB-ALLOW-HTTPS
```

- **Purpose:** Show the hit count for one rule on supported PAN-OS versions.
- **Arguments:** vsys: virtual system; rule-name: security policy name.
- **Use case:** Confirm the new policy is being used, instead of just existing.
- **Caution:** Some rules require rule-hit-count to be enabled/supported.

> Quick reference, not lab-verified. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Official documentation 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Official documentation 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
