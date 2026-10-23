---
tags: [cli, cisco, ios, troubleshooting]
vendor: Cisco
os: "IOS"
validation: not-lab-verified
---

# 🛠️ Troubleshooting

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Cisco](../README.md)

**Platform:** Cisco / IOS · **Reference versions:** IOS 15.x (classic; feature availability varies). Confirm each command on the installed release.

## `ping 192.0.2.10`

```text
ping 192.0.2.10
```

- **Purpose:** Test IPv4 reachability.
- **Arguments:** 192.0.2.10: destination.
- **Use case:** Verify access to a lab host.

- **Practical filter:** `show ip route 192.0.2.10` — Filter or verify relevant output; inspect full output when additional context is needed.

## `traceroute 192.0.2.10`

```text
traceroute 192.0.2.10
```

- **Purpose:** Trace hops toward a destination.
- **Arguments:** 192.0.2.10: destination.
- **Use case:** Locate where a path stops.

- **Practical filter:** `show ip route 192.0.2.10` — Filter or verify relevant output; inspect full output when additional context is needed.

## `show interfaces GigabitEthernet0/0`

```text
show interfaces GigabitEthernet0/0
```

- **Purpose:** Inspect status and interface errors.
- **Arguments:** GigabitEthernet0/0: device-specific interface name.
- **Use case:** Look for CRC errors.

- **Practical filter:** `show logging | include LINK|LINEPROTO` — Filter or verify relevant output; inspect full output when additional context is needed.

## `show logging`

```text
show logging | include LINK|LINEPROTO
```

- **Purpose:** Display system log messages.
- **Arguments:** No options.
- **Use case:** Find a link-down event.

- **Practical filter:** `show interfaces GigabitEthernet0/0 | include errors|drops|CRC` — Filter or verify relevant output; inspect full output when additional context is needed.


> Short reference, not lab-verified. Validate using built-in CLI help and documentation for your model/release.

**Vendor documentation:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_pi/configuration/15-mt/iri-15-mt-book/iri-iprouting.html · https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/interface/configuration/15-mt/ir-15-mt-book/ir-cfg-vir-if.html
