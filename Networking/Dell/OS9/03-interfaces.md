---
tags: [cli, dell, os9, interfaces]
validation: not-lab-verified
---

# Interfaces — Dell OS9

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Index](README.md)

**Compatibility:** Dell Networking OS9 / Force10; confirm the platform and FTOS-derived CLI. Verify with `show version` and `?`.

## `show interfaces tengigabitethernet 0/1`

```text
show interfaces tengigabitethernet 0/1
```

- **Purpose:** Inspect one link on a compatible Force10 switch.
- **Options:** Interface name: verify unit/port.
- **Real use:** Check uplink CRC/errors.

## `show running-config`

```text
show running-config | grep hostname
```

- **Purpose:** Review interface configuration before changes.
- **Options:** No flags.
- **Real use:** Identify interface block.

## `interface tengigabitethernet 0/1`

```text
configure
interface tengigabitethernet 0/1
 description LAB-UPLINK
exit
end
```

- **Purpose:** Label an uplink on a compatible OS9 platform.
- **Options:** interface: physical port; description: label.
- **Real use:** Label a lab port.

## `show interfaces description | grep UPLINK`

```text
show interfaces description | grep UPLINK
```

- **Purpose:** Filter Force10/OS9 interface descriptions by the uplink label.
- **Options:** show interfaces description: port description table; | grep: matching lines.
- **Real use:** Locate the port connecting a core switch to a firewall.
- **Compatibility:** Dell OS9 / FTOS; validate filtering syntax with `?` for the release.
- **Reference:** [Vendor documentation](https://www.dell.com/support/manuals/en-us/smartfabric-os10-emp-partner/techsheet-os10-5-x-os9-pub/interfaces?guid=guid-9097a31b-e5b3-4702-909e-b8587224aa1f&lang=en-us)

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://i.dell.com/sites/doccontent/shared-content/data-sheets/en/Documents/ESG-Dell-Force10-FTOS-CLI-Spec-Sheet.pdf)
