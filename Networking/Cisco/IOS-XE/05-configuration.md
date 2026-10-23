---
tags: [cli, cisco, ios-xe, configuration]
vendor: Cisco
os: "IOS XE"
validation: not-lab-verified
---

# ⚙️ General configuration

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Cisco](../README.md)

**Platform:** Cisco / IOS XE · **Reference versions:** IOS XE 17.x. Confirm each command on the installed release.

## Set hostname

```text
configure terminal
hostname RTR-LAB
end
```

**Verify with:**

```text
show running-config | include ^hostname
```


- **Purpose:** Set the device hostname.
- **Arguments:** configure terminal: enter config; hostname: device name; end: exit.
- **Use case:** Identify a lab router.

- **Verification:** `show running-config | include ^hostname` — Filter or verify relevant data; inspect full output when more context is needed.

## Configure Loopback0

```text
configure terminal
interface Loopback0
 ip address 192.0.2.1 255.255.255.255
end
```

**Verify with:**

```text
show ip interface brief | include Loopback0
```


- **Purpose:** Create a loopback with an IPv4 /32 address.
- **Arguments:** interface Loopback0: virtual interface; ip address: IP and mask.
- **Use case:** Use a stable router ID in a lab.

- **Verification:** `show ip interface brief | include Loopback0` — Filter or verify relevant data; inspect full output when more context is needed.

## Add static route

```text
configure terminal
ip route 198.51.100.0 255.255.255.0 192.0.2.254
end
```

**Verify with:**

```text
show ip route 198.51.100.10
```


- **Purpose:** Install an IPv4 static route.
- **Arguments:** ip route: destination, mask, next-hop IP.
- **Use case:** Reach a second lab segment.
- **Caution:** Ensure the next hop is reachable before deployment.

- **Verification:** `show ip route 198.51.100.10` — Filter or verify relevant data; inspect full output when more context is needed.

## Configure buffered logging

```text
configure terminal
logging buffered 16384
end
```

**Verify with:**

```text
show running-config | include logging buffered
```


- **Purpose:** Enable a bounded in-memory logging buffer.
- **Arguments:** 16384: desired buffer size in bytes (platform limits vary).
- **Use case:** Review messages using show logging.

- **Verification:** `show running-config | include logging buffered` — Filter or verify relevant data; inspect full output when more context is needed.

## Configure log timestamps

```text
configure terminal
service timestamps log datetime msec
end
```

**Verify with:**

```text
show running-config | include service timestamps
```


- **Purpose:** Add timestamps with milliseconds to log messages.
- **Arguments:** log: syslog messages; datetime: date/time; msec: milliseconds.
- **Use case:** Correlate events by time.

- **Verification:** `show running-config | include service timestamps` — Filter or verify relevant data; inspect full output when more context is needed.

## `copy running-config startup-config`

```text
copy running-config startup-config
```

- **Purpose:** Save current running configuration.
- **Arguments:** running-config: source; startup-config: saved destination.
- **Use case:** Persist tested configuration over a reload.
- **Caution:** Only save changes you intend to keep.

- **Verification:** `show running-config | include ^hostname|^ip route` — Filter or verify relevant data; inspect full output when more context is needed.


> Short reference, not lab-verified. Validate using built-in CLI help and documentation for your model/release.

**Vendor documentation:** https://www.cisco.com/c/en/us/td/docs/routers/access/isr1100/software/configuration/xe-17/isr1100-sw-config-xe-17/using_iosxe_software.pdf · https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/interface/configuration/15-mt/ir-15-mt-book/ir-cfg-vir-if.html · https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_pi/configuration/15-mt/iri-15-mt-book/iri-iprouting.html
