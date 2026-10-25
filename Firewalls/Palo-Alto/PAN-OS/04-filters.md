---
tags: [cli, palo-alto-networks, pan-os, filters]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Output filters & targeted lookups

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ PAN-OS index](README.md)

**Platform:** Palo Alto Networks / PAN-OS · **Compatibility:** Verify the installed version with `show system info | match sw-version`. Commands vary by release, platform, vsys and routing mode.

## `show system info | match serial`

```text
show system info | match serial
```

- **Purpose:** Show only lines containing a serial identifier.
- **Arguments:** | match: matches output text; PAN-OS is not Linux grep.
- **Use case:** Locate an inventory identifier during an audit.

## `show system info | except mac-address`

```text
show system info | except mac-address
```

- **Purpose:** Hide lines matching a keyword.
- **Arguments:** | except: display nonmatching lines.
- **Use case:** Share a short system view without unrelated MAC fields.
- **Caution:** This is not sanitization: outputs may still contain sensitive values.

## `show vpn ike-sa | match LAB-IKE`

```text
show vpn ike-sa | match LAB-IKE
```

- **Purpose:** Search active IKE SA output for the named gateway.
- **Arguments:** | match: case-sensitive output filter.
- **Use case:** Find whether the lab VPN has an IKE SA.
- **Caution:** For full details use the gateway-specific operational command.

## `show running nat-policy | match LAB-NAT`

```text
show running nat-policy | match LAB-NAT
```

- **Purpose:** Locate the named NAT rule in running policy.
- **Arguments:** | match: show matching policy lines.
- **Use case:** Check a named NAT rule during troubleshooting.

## `show session all filter application ssl`

```text
show session all filter application ssl
```

- **Purpose:** Show sessions with a specific App-ID label.
- **Arguments:** filter application: built-in session filter.
- **Use case:** Isolate TLS sessions without enumerating every session.
- **Caution:** Only sessions identified with that App-ID are matched.

> Quick reference, not lab-verified. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Official documentation 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/get-started-with-the-cli/get-help-on-command-syntax) · [Official documentation 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Official documentation 3](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
