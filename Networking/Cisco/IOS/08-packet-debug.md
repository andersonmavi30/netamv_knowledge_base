---
tags: [cli, packet-capture, debugging]
validation: not-lab-verified
---

# 🧪 Packet capture & debugging — Cisco IOS

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Index](README.md)

**Reference version:** Classic IOS (EPC supported only on certain platforms/trains).

> ⚠️ Captures and debugging may consume resources or expose sensitive data. Use only on authorized networks, scope carefully and always stop afterward.

## monitor capture buffer LABBUF size 256 max-size 100 circular

```text
monitor capture buffer LABBUF size 256 max-size 100 circular
monitor capture point ip cef LABPOINT FastEthernet0/0 both
monitor capture point associate LABPOINT LABBUF
monitor capture point start LABPOINT
```

- **Purpose:** Start a bounded embedded packet capture where classic IOS EPC is supported.
- **Parameters:** size 256: buffer KB; max-size 100: bytes per packet; both: directions; associate: attach buffer.
- **Real-world use:** Troubleshoot packets on a lab FastEthernet interface; use on-device help to check support.

## monitor capture point stop LABPOINT

```text
monitor capture point stop LABPOINT
show monitor capture buffer LABBUF dump
no monitor capture point ip cef LABPOINT FastEthernet0/0 both
no monitor capture buffer LABBUF
```

- **Purpose:** Stop, inspect and remove an IOS EPC capture.
- **Parameters:** stop: end capture; dump: packet bytes; no: delete capture point/buffer.
- **Real-world use:** Release capture resources after a short test.

## debug ip ospf adj

```text
debug ip ospf adj
undebug all
```

- **Purpose:** Inspect OSPF adjacency events briefly; stop all debug afterward.
- **Parameters:** adj: adjacency debugging; undebug all: stop all active debugs.
- **Real-world use:** Investigate a neighbor stuck before FULL.

**Vendor reference:** https://www.cisco.com/c/en/us/support/docs/ios-nx-os-software/ios-embedded-packet-capture/116045-productconfig-epc-00.html

**Note:** EPC/sniffer may not see hardware-offloaded packets. Protocol debugging is not the same as PCAP.
