---
tags: [cli, fortinet, fortios, configuration]
vendor: Fortinet
os: "FortiOS"
validation: not-lab-verified
---

# ⚙️ General configuration

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Fortinet](../README.md)

**Platform:** Fortinet / FortiOS · **Reference versions:** FortiOS 7.x. Confirm each command on the installed release.

## `config system global`

```text
config system global
    set hostname FGT-LAB
end
```

**Verify with:**

```text
get system status | grep -i hostname
```


- **Purpose:** Change the firewall hostname.
- **Arguments:** set hostname: new device name; end: apply and leave.
- **Use case:** Name a lab FortiGate.

- **Verify:** `get system status | grep -i hostname` — Verify the saved hostname.

## `config system dns`

```text
config system dns
    set primary 1.1.1.1
    set secondary 9.9.9.9
end
```

**Verify with:**

```text
show system dns | grep -i primary
```


- **Purpose:** Set the device's DNS resolvers.
- **Arguments:** primary: preferred DNS; secondary: backup DNS.
- **Use case:** Resolve FQDNs from the firewall.
- **Caution:** Changing DNS can affect updates and FQDN objects.

- **Verify:** `show system dns | grep -i primary` — Verify the primary DNS resolver.

## `config firewall address`

```text
config firewall address
    edit "LAB-NET"
        set subnet 192.0.2.0 255.255.255.0
    next
end
```

**Verify with:**

```text
show firewall address | grep -f LAB-NET
```


- **Purpose:** Create an IPv4 subnet address object.
- **Arguments:** edit: object name; set subnet: network and mask; next: save.
- **Use case:** Reference LAB-NET in a test policy.

- **Verify:** `show firewall address | grep -f LAB-NET` — Review the created object.

## `config firewall addrgrp`

```text
config firewall addrgrp
    edit "LAB-SOURCES"
        set member "LAB-NET"
    next
end
```

**Verify with:**

```text
show firewall addrgrp | grep -f LAB-SOURCES
```


- **Purpose:** Create an address group from an existing object.
- **Arguments:** set member: list of existing address objects; replaces existing members.
- **Use case:** Group lab source addresses.
- **Caution:** Confirm LAB-NET exists; set member may overwrite previous members.

- **Verify:** `show firewall addrgrp | grep -f LAB-SOURCES` — Review the address group's members.

## `config router static`

```text
config router static
    edit 0
        set dst 198.51.100.0 255.255.255.0
        set gateway 192.0.2.254
        set device "port3"
    next
end
```

**Verify with:**

```text
get router info routing-table all | grep 198.51.100
```


- **Purpose:** Add a static IPv4 route.
- **Arguments:** edit 0: create a new entry; dst: destination/mask; gateway: next hop; device: egress interface.
- **Use case:** Route a lab network through port3.
- **Caution:** Assumes port3 reaches 192.0.2.254; incorrect routes disrupt traffic.

- **Verify:** `get router info routing-table all | grep 198.51.100` — Look for the installed route; check reachability separately.

## `config firewall service custom`

```text
config firewall service custom
    edit "LAB-HTTPS-8443"
        set tcp-portrange 8443
    next
end
```

**Verify with:**

```text
show firewall service custom | grep -f LAB-HTTPS-8443
```


- **Purpose:** Define a custom TCP service for policies.
- **Arguments:** tcp-portrange: TCP destination port or range.
- **Use case:** Use port 8443 in a lab policy.

- **Verify:** `show firewall service custom | grep -f LAB-HTTPS-8443` — Review custom TCP service settings.


> Short reference, not lab-verified. Validate using built-in CLI help and documentation for your model/release.

**Vendor documentation:** https://docs.fortinet.com/document/fortigate/7.4.2/administration-guide/777334/basic-configuration · https://docs.fortinet.com/document/fortigate/7.6.6/cli-reference/200835411/config-router-static
