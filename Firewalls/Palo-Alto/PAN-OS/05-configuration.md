---
tags: [cli, palo-alto-networks, pan-os, configuration]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Configuration examples

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ PAN-OS index](README.md)

**Platform:** Palo Alto Networks / PAN-OS · **Compatibility:** Verify the installed version with `show system info | match sw-version`. Commands vary by release, platform, vsys and routing mode.

## Set lab firewall hostname

```text
configure
set deviceconfig system hostname PA-LAB
```

**Verify candidate configuration:**

```text
show deviceconfig system | match hostname
```

- **Purpose:** Set a hostname in the candidate configuration and read it back.
- **Arguments:** configure: config mode; set: candidate change; show: view candidate; commit: separate action.
- **Use case:** Identify a lab firewall without immediately committing.
- **Caution:** No production commit until peer review and connectivity check.

## Set primary DNS for management

```text
configure
set deviceconfig system dns-setting servers primary 192.0.2.53
```

**Verify candidate configuration:**

```text
show deviceconfig system dns-setting servers
```

- **Purpose:** Set the management-plane DNS primary server in candidate config.
- **Arguments:** primary: preferred resolver; show: candidate validation.
- **Use case:** Prepare a lab DNS change and verify selected value.
- **Caution:** Changing DNS can affect updates and FQDN objects once committed.

## Create an IP address object

```text
configure
set address LAB-HOST ip-netmask 192.0.2.10
```

**Verify candidate configuration:**

```text
show address LAB-HOST
```

- **Purpose:** Define a host address object in the current vsys.
- **Arguments:** address: object name; ip-netmask: host/prefix; show: candidate check.
- **Use case:** Prepare a lab address object for later use in policy.
- **Caution:** Verify vsys/Panorama ownership before changing shared objects.

## Assign Layer 3 IPv4 interface address

```text
configure
set network interface ethernet ethernet1/3 layer3 ip 192.0.2.1/24
```

**Verify candidate configuration:**

```text
show network interface ethernet ethernet1/3
```

- **Purpose:** Add an interface IPv4 address to the candidate configuration.
- **Arguments:** ethernet1/3: physical interface; layer3: interface mode; ip: CIDR.
- **Use case:** Stage LAN interface addressing in an isolated lab.
- **Caution:** Changing interface mode/IP can interrupt remote connectivity after commit.

## Validate and apply a reviewed candidate

```text
configure
show | match LAB-HOST
commit
```

- **Purpose:** Commit reviewed candidate changes to running configuration.
- **Arguments:** show: inspect candidate; commit: activate candidate changes.
- **Use case:** Apply an approved change window after prechecks.
- **Caution:** Commit applies all included pending changes; coordinate with concurrent admins.

> Quick reference, not lab-verified. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Official documentation 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/use-the-cli/cli-jump-start) · [Official documentation 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/get-started-with-the-cli/get-help-on-command-syntax)
