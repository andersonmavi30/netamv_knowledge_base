---
tags: [cli, cisco, ios, interfaces]
vendor: Cisco
os: "IOS"
validation: not-lab-verified
---

# 🔌 Interface configuration

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Cisco](../README.md)

**Platform:** Cisco / IOS · **Reference versions:** IOS 15.x (classic; feature availability varies). Confirm each command on the installed release.

## `configure terminal`

```text
configure terminal
interface GigabitEthernet0/0
 description LAB-LAN
 ip address 192.0.2.1 255.255.255.0
 no shutdown
end
```

- **Purpose:** Set an interface's IPv4 address and enable it.
- **Arguments:** description: label; ip address: IP and mask; no shutdown: enable port.
- **Use case:** Bring up a lab LAN interface.
- **Caution:** Changing a production interface can interrupt connectivity.

- **Practical filter:** `show running-config | section ^interface GigabitEthernet0/0` — Filter or verify relevant output; inspect full output when additional context is needed.

## `show ip interface brief`

```text
show ip interface brief
```

- **Purpose:** Verify configured addresses and interface state.
- **Arguments:** brief: concise output.
- **Use case:** Confirm IP and up/up.

- **Practical filter:** `show ip interface brief | include GigabitEthernet0/0` — Filter or verify relevant output; inspect full output when additional context is needed.

## `show running-config interface GigabitEthernet0/0`

```text
show running-config interface GigabitEthernet0/0
```

- **Purpose:** Display interface configuration on supported IOS trains.
- **Arguments:** Interface name: replace to match your model.
- **Use case:** Review LAN interface settings.

- **Practical filter:** `show ip interface brief | include GigabitEthernet0/0` — Filter or verify relevant output; inspect full output when additional context is needed.

## `copy running-config startup-config`

```text
copy running-config startup-config
```

- **Purpose:** Save active configuration to startup.
- **Arguments:** running-config: source; startup-config: destination.
- **Use case:** Preserve tested changes.

- **Practical filter:** `show running-config | section ^interface GigabitEthernet0/0` — Filter or verify relevant output; inspect full output when additional context is needed.


> Short reference, not lab-verified. Validate using built-in CLI help and documentation for your model/release.

**Vendor documentation:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/interface/configuration/15-mt/ir-15-mt-book/ir-cfg-vir-if.html
