---
tags: [cli, juniper, junos]
validation: not-lab-verified
---

# Interfaces and optics

[English](03-interfaces.md) · [Español](03-interfaces.es.md) · [Index](README.md)

**Compatibility:** Junos OS; verify model, release and `?`.

## `show interfaces terse`

```text
show interfaces terse
```

- **Purpose:** Summarize physical and logical interface administrative and link states.
- **Arguments:** terse: concise status and address table; inet entries show IPv4 addresses.
- **Use case:** Find interfaces down or with unexpected IP addresses.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-interfaces-gigabit-ethernet.html

> Not lab-verified.

## `show interfaces diagnostics optics ge-0/0/0`

```text
show interfaces diagnostics optics ge-0/0/0
```

- **Purpose:** Inspect optical receive/transmit power and transceiver sensor alarms.
- **Arguments:** diagnostics optics: DOM metrics; ge-0/0/0: target port; optics must support DOM.
- **Use case:** Diagnose low optical receive power on an uplink.
- **Official reference:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-interfaces-security.html

> Not lab-verified.
