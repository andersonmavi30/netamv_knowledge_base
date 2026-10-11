---
tags: [cli, cisco, ios, show]
vendor: Cisco
os: "IOS"
validation: not-lab-verified
---

# 🔎 Show & status

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Cisco](../README.md)

**Platform:** Cisco / IOS · **Reference versions:** IOS 15.x (classic; feature availability varies). Confirm each command on the installed release.

## `show version`

```text
show version
```

- **Purpose:** Show Cisco IOS release, hardware and uptime.
- **Arguments:** No options.
- **Use case:** Identify the IOS release before a change.

## `show ip interface brief`

```text
show ip interface brief
```

- **Purpose:** Summarize IPv4 addresses and link state.
- **Arguments:** brief: concise view.
- **Use case:** Check that GigabitEthernet0/0 is up/up.

## `show ip route`

```text
show ip route
```

- **Purpose:** Display the IPv4 routing table.
- **Arguments:** No options.
- **Use case:** Find an active route.

## `show running-config`

```text
show running-config
```

- **Purpose:** Inspect the active device configuration.
- **Arguments:** No options.
- **Use case:** Review before changing a device.

> Short reference, not lab-verified. Validate using built-in CLI help and documentation for your model/release.

**Vendor documentation:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_pi/configuration/15-mt/iri-15-mt-book/iri-iprouting.html
