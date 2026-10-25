---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Configuration

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Index](README.md)

**Compatibility:** AOS-CX 10.x; verify model and release.

## `hostname CX-LAB`

```text
configure terminal
hostname CX-LAB
end
```

**Verify with:**

```text
show running-config | include hostname
```

- **Purpose:** Set the switch hostname.
- **Arguments:** hostname: device identity.
- **Use case:** Name a lab switch.

## `vlan 10`

```text
configure terminal
vlan 10
name USERS
end
```

**Verify with:**

```text
show vlan | include 10
```

- **Purpose:** Create and label VLAN 10.
- **Arguments:** vlan: ID; name: label.
- **Use case:** Prepare lab subnet.

## `interface 1/1/2`

```text
configure terminal
interface 1/1/2
no routing
vlan access 10
no shutdown
end
```

**Verify with:**

```text
show running-config | begin interface 1/1/2
```

- **Purpose:** Configure a Layer 2 access port.
- **Arguments:** no routing: Layer 2; vlan access: VLAN.
- **Use case:** Connect a lab host.

## `copy running-config startup-config`

```text
copy running-config startup-config
```

**Verify with:**

```text
show startup-config | include hostname
```

- **Purpose:** Save the approved configuration.
- **Arguments:** running-config: source; startup-config: saved.
- **Use case:** Keep verified changes.

> Lab validation required. Mirror/tshark need platform support and authorization; disable after use.
