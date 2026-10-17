---
tags: [cli, dell, os10, interfaces]
validation: not-lab-verified
---

# Interfaces — Dell OS10

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Index](README.md)

**Compatibility:** Dell SmartFabric OS10 (PowerSwitch hardware/release dependent). Verify with `show version` and `?`.

## `show running-configuration interface ethernet 1/1/2`

```text
show running-configuration interface ethernet 1/1/2
```

- **Purpose:** Review one interface's running configuration.
- **Options:** ethernet 1/1/2: physical port.
- **Real use:** Inspect current uplink role.

## `show interface phy-eth 1/1/2`

```text
show interface phy-eth 1/1/2
```

- **Purpose:** Inspect physical transceiver/link details.
- **Options:** phy-eth: physical media status.
- **Real use:** Diagnose transceiver fault.

## `interface ethernet 1/1/2`

```text
configure terminal
interface ethernet 1/1/2
 description LAB-UPLINK
 exit
end
```

- **Purpose:** Label a lab uplink.
- **Options:** interface: physical port; description: label.
- **Real use:** Identify correct cable.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://www.dell.com/support/manuals/en-us/dell-emc-smartfabric-os10/smartfabric-os-user-guide-10-5-0/Filter-show-commands?guid=guid-758c857a-eba2-477a-a8f5-f0738c185e54&lang=en-us)
