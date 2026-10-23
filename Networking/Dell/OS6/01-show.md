---
tags: [cli, dell, os6, show]
validation: not-lab-verified
---

# Show & status — Dell OS6

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Index](README.md)

**Compatibility:** OS6 / N-Series; CLI output filtering is available in OS6 6.6+ where supported. Verify with `show version` and `?`.

## `show version`

```text
show version | include Version
```

- **Purpose:** Identify switch software and hardware.
- **Options:** No flags.
- **Real use:** Confirm OS6 before commands.

## `show interfaces status`

```text
show interfaces status | include 1/0/1
```

- **Purpose:** List physical port operational states.
- **Options:** status: compact view.
- **Real use:** Locate inactive links.

## `show vlan`

```text
show vlan | include 10
```

- **Purpose:** List configured VLANs.
- **Options:** No flags.
- **Real use:** Find VLAN 10.

## `show ip route`

```text
show ip route | include 198.51.100
```

- **Purpose:** Display IPv4 routing information.
- **Options:** No flags; requires L3 capability.
- **Real use:** Check default route.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)
