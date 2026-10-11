---
tags: [cli, cisco, ios, filters]
vendor: Cisco
os: "IOS"
validation: not-lab-verified
---

# 🔍 Output filters

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Cisco](../README.md)

**Platform:** Cisco / IOS · **Reference versions:** IOS 15.x (classic; feature availability varies). Confirm each command on the installed release.

## `show ip interface brief | include GigabitEthernet`

```text
show ip interface brief | include GigabitEthernet
```

- **Purpose:** Include only matching lines.
- **Arguments:** |: pipe; include: matching lines.
- **Use case:** List GigabitEthernet only.

- **Practical filter:** `show ip interface brief | include GigabitEthernet0/0` — Filter or verify relevant output; inspect full output when additional context is needed.

## `show logging | exclude LINK`

```text
show logging | exclude LINK
```

- **Purpose:** Hide messages that match LINK.
- **Arguments:** exclude: discard matching lines.
- **Use case:** Focus on other errors.

- **Practical filter:** `show logging | include LINK|LINEPROTO` — Filter or verify relevant output; inspect full output when additional context is needed.

## `show running-config | begin interface`

```text
show running-config | begin interface
```

- **Purpose:** Display output starting at the first match.
- **Arguments:** begin: first matching line and everything after.
- **Use case:** Skip the global header.

- **Practical filter:** `show running-config | section ^interface GigabitEthernet0/0` — Filter or verify relevant output; inspect full output when additional context is needed.

## `show running-config | section router`

```text
show running-config | section router
```

- **Purpose:** Display configuration sections beginning with router.
- **Arguments:** section: match a configuration section.
- **Use case:** Read routing process config.

- **Practical filter:** `show ip route 198.51.100.10` — Filter or verify relevant output; inspect full output when additional context is needed.


> Short reference, not lab-verified. Validate using built-in CLI help and documentation for your model/release.

**Vendor documentation:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_pi/configuration/15-mt/iri-15-mt-book/iri-iprouting.html
