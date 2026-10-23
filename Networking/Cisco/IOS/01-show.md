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
show version | include IOS|uptime
```

- **Purpose:** Show Cisco IOS release, hardware and uptime.
- **Arguments:** No options.
- **Use case:** Identify the IOS release before a change.

- **Practical filter:** `show version | include IOS|uptime` — Filter or verify relevant output; inspect full output when additional context is needed.

## `show ip interface brief`

```text
show ip interface brief | include GigabitEthernet
```

- **Purpose:** Summarize IPv4 addresses and link state.
- **Arguments:** brief: concise view.
- **Use case:** Check that GigabitEthernet0/0 is up/up.

- **Practical filter:** `show ip interface brief | include GigabitEthernet` — Filter or verify relevant output; inspect full output when additional context is needed.

## `show ip route`

```text
show ip route 198.51.100.10
```

- **Purpose:** Display the IPv4 routing table.
- **Arguments:** No options.
- **Use case:** Find an active route.

- **Practical filter:** `show ip route 198.51.100.10` — Filter or verify relevant output; inspect full output when additional context is needed.

## `show running-config`

```text
show running-config | include ^hostname
```

- **Purpose:** Inspect the active device configuration.
- **Arguments:** No options.
- **Use case:** Review before changing a device.

- **Practical filter:** `show interfaces GigabitEthernet0/0 | include line protocol|errors|drops` — Filter or verify relevant output; inspect full output when additional context is needed.


> Short reference, not lab-verified. Validate using built-in CLI help and documentation for your model/release.

**Vendor documentation:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_pi/configuration/15-mt/iri-15-mt-book/iri-iprouting.html
