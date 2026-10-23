---
tags: [cli, fortinet, fortios, interfaces]
vendor: Fortinet
os: "FortiOS"
validation: not-lab-verified
---

# 🔌 Interface configuration

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Fortinet](../README.md)

**Platform:** Fortinet / FortiOS · **Compatibility:** FortiOS 7.x (verify your exact release).

## `show system interface`

```text
show system interface | grep -f port3
```

- **Purpose:** Display existing interface configuration.
- **Arguments:** No arguments.
- **Use case:** Review before changing an interface.

- **Practical filter:** `show system interface | grep -f port3` — See the port's configuration block with context.

## `config system interface`

```text
config system interface
    edit "port3"
        set alias "LAB-LAN"
        set ip 192.0.2.1 255.255.255.0
        set allowaccess ping
    next
end
```

- **Purpose:** Configure a lab interface IPv4 address, alias and management access.
- **Arguments:** edit: select port3; set ip: IPv4/netmask; set allowaccess: permitted management protocols; next/end: save and exit.
- **Use case:** Enable ICMP management on an isolated lab LAN.
- **Caution:** Changes take effect immediately. set allowaccess replaces the previous protocol list; never paste blindly in production.

- **Practical filter:** `show system interface | grep -f port3` — Validate port3 IP, alias and access after applying changes.


> **Note:** Quick reference, not lab-verified; confirm syntax and permissions on your model and release.

**Vendor reference:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966
