---
tags: [cli, palo-alto-networks, pan-os, filters]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# 🔍 Output filters & targeted lookups

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ PAN-OS index](README.md)

**Compatibility:** PAN-OS (revisar versión exacta con `show system info | match sw-version`). Commands vary by release, platform, vsys and routing mode.

## Use PAN-OS match instead of grep

```text
show system info | match serial
```

- **Purpose:** Show only lines containing a serial identifier.
- **Parameters and filters:** | match: matches output text; PAN-OS is not Linux grep.
- **Operational use:** Locate an inventory identifier during an audit.

## Exclude noisy output lines

```text
show system info | except mac-address
```

- **Purpose:** Hide lines matching a keyword.
- **Parameters and filters:** | except: display nonmatching lines.
- **Operational use:** Share a short system view without unrelated MAC fields.
- **Caution:** This is not sanitization: outputs may still contain sensitive values.

## Filter established VPN gateways

```text
show vpn ike-sa | match LAB-IKE
```

- **Purpose:** Search active IKE SA output for the named gateway.
- **Parameters and filters:** | match: case-sensitive output filter.
- **Operational use:** Find whether the lab VPN has an IKE SA.
- **Caution:** For full details use the gateway-specific operational command.

## Filter NAT policies by rule name

```text
show running nat-policy | match LAB-NAT
```

- **Purpose:** Locate the named NAT rule in running policy.
- **Parameters and filters:** | match: show matching policy lines.
- **Operational use:** Check a named NAT rule during troubleshooting.

## View sessions by application

```text
show session all filter application ssl
```

- **Purpose:** Show sessions with a specific App-ID label.
- **Parameters and filters:** filter application: built-in session filter.
- **Operational use:** Isolate TLS sessions without enumerating every session.
- **Caution:** Only sessions identified with that App-ID are matched.

> Illustrative examples pending lab testing. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Docs 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/get-started-with-the-cli/get-help-on-command-syntax) · [Docs 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Docs 3](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
