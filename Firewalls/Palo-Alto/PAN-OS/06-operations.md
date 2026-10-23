---
tags: [cli, palo-alto-networks, pan-os, operations]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# 🧭 VPN, policy & operational checks

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ PAN-OS index](README.md)

**Compatibility:** PAN-OS (revisar versión exacta con `show system info | match sw-version`). Commands vary by release, platform, vsys and routing mode.

## Inspect one IKE gateway

```text
show vpn ike-sa gateway LAB-IKE
```

- **Purpose:** Find Phase 1 SAs by gateway name.
- **Parameters and filters:** gateway: configured IKE gateway name.
- **Operational use:** Investigate phase 1 negotiation failure.

## Inspect IPsec tunnel SAs

```text
show vpn ipsec-sa tunnel LAB-IPSEC
```

- **Purpose:** Find Phase 2 SAs for a named tunnel.
- **Parameters and filters:** tunnel: selected IPsec tunnel.
- **Operational use:** Determine whether phase 2 is installed.

## View VPN packet counters

```text
show vpn flow name LAB-IPSEC
```

- **Purpose:** Inspect packets and tunnel flow status for one IPsec tunnel.
- **Parameters and filters:** name: tunnel name.
- **Operational use:** Check if encrypted tunnel counters change with test traffic.

## Locate a security policy

```text
show running security-policy | match LAB-ALLOW-HTTPS
```

- **Purpose:** Search installed security policy output by name.
- **Parameters and filters:** match: exact text matching on output lines.
- **Operational use:** Verify intended policy is in the running rulebase.

## Inspect a rule's hit count

```text
show running rule-use hit-count vsys vsys1 rule-base security rules rule-name LAB-ALLOW-HTTPS
```

- **Purpose:** Show the hit count for one rule on supported PAN-OS versions.
- **Parameters and filters:** vsys: virtual system; rule-name: security policy name.
- **Operational use:** Confirm the new policy is being used, instead of just existing.
- **Caution:** Some rules require rule-hit-count to be enabled/supported.

> Illustrative examples pending lab testing. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Docs 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Docs 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
