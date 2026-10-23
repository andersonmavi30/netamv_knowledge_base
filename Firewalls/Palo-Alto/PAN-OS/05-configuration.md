---
tags: [cli, palo-alto-networks, pan-os, configuration]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# ⚙️ Configuration examples

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ PAN-OS index](README.md)

**Compatibility:** PAN-OS (revisar versión exacta con `show system info | match sw-version`). Commands vary by release, platform, vsys and routing mode.

## Set lab firewall hostname

```text
configure
set deviceconfig system hostname PA-LAB
show deviceconfig system | match hostname
```

- **Purpose:** Set a hostname in the candidate configuration and read it back.
- **Parameters and filters:** configure: config mode; set: candidate change; show: view candidate; commit: separate action.
- **Operational use:** Identify a lab firewall without immediately committing.
- **Caution:** No production commit until peer review and connectivity check.

## Set primary DNS for management

```text
configure
set deviceconfig system dns-setting servers primary 192.0.2.53
show deviceconfig system dns-setting servers
```

- **Purpose:** Set the management-plane DNS primary server in candidate config.
- **Parameters and filters:** primary: preferred resolver; show: candidate validation.
- **Operational use:** Prepare a lab DNS change and verify selected value.
- **Caution:** Changing DNS can affect updates and FQDN objects once committed.

## Create an IP address object

```text
configure
set address LAB-HOST ip-netmask 192.0.2.10
show address LAB-HOST
```

- **Purpose:** Define a host address object in the current vsys.
- **Parameters and filters:** address: object name; ip-netmask: host/prefix; show: candidate check.
- **Operational use:** Prepare a lab address object for later use in policy.
- **Caution:** Verify vsys/Panorama ownership before changing shared objects.

## Assign Layer 3 IPv4 interface address

```text
configure
set network interface ethernet ethernet1/3 layer3 ip 192.0.2.1/24
show network interface ethernet ethernet1/3
```

- **Purpose:** Add an interface IPv4 address to the candidate configuration.
- **Parameters and filters:** ethernet1/3: physical interface; layer3: interface mode; ip: CIDR.
- **Operational use:** Stage LAN interface addressing in an isolated lab.
- **Caution:** Changing interface mode/IP can interrupt remote connectivity after commit.

## Validate and apply a reviewed candidate

```text
configure
show | match LAB-HOST
commit
```

- **Purpose:** Commit reviewed candidate changes to running configuration.
- **Parameters and filters:** show: inspect candidate; commit: activate candidate changes.
- **Operational use:** Apply an approved change window after prechecks.
- **Caution:** Commit applies all included pending changes; coordinate with concurrent admins.

> Illustrative examples pending lab testing. Use contextual `?` help and confirm operational (`>`) versus configuration (`#`) mode before use.

**Official references:** [Docs 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/use-the-cli/cli-jump-start) · [Docs 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/get-started-with-the-cli/get-help-on-command-syntax)
