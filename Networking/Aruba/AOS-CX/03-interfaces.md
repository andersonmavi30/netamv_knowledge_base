---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Interface checks

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Index](README.md)

**Compatibility:** AOS-CX 10.x; verify installed release with `show version` and `?`.

## `show interface 1/1/3`

```text
show interface 1/1/3
```

- **Purpose:** Check one port counters.
- **Arguments:** 1/1/3: target interface.
- **Use case:** Diagnose link errors.

## `show ip interface brief | include vlan10`

```text
show ip interface brief | include vlan10
```

- **Purpose:** Find SVI IPv4 information.
- **Arguments:** include: VLAN interface text.
- **Use case:** Check management gateway.

## `show running-config | begin interface 1/1/3`

```text
show running-config | begin interface 1/1/3
```

- **Purpose:** Inspect configuration from a port onward.
- **Arguments:** begin: first match and remainder.
- **Use case:** Review port settings.

## `show interface brief | include down`

```text
show interface brief | include down
```

- **Purpose:** Find down ports.
- **Arguments:** include: matching lines.
- **Use case:** Find inactive links.

## `show interface brief | include UPLINK`

```text
show interface brief | include UPLINK
```

**Single-port alternative:**

```text
show interface 1/1/1 | include Description
```

- **Purpose:** Locate switch ports whose Description column contains UPLINK; inspect a single port if the summary omits labels.
- **Arguments:** brief: condensed interface status (and descriptions where supported); | include: matching lines.
- **Use case:** Find the upstream switch port, then check its configured description and link state.
- **Compatibility:** AOS-CX; whether descriptions appear in `brief` depends on release/platform.
- **Reference:** [Vendor documentation](https://arubanetworking.hpe.com/techdocs/AOS-CX/10.16/HTML/fundamentals_8100-83xx-93xx-100xx/Content/Chp_IfaceCfg/Iface_cmds/sho-int-10.htm)

> Examples pending lab validation; availability varies by release and hardware.
