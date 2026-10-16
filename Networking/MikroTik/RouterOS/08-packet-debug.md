---
tags: [cli, packet-capture, debugging]
validation: not-lab-verified
---

# 🧪 Packet capture & debugging — MikroTik RouterOS

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Index](README.md)

**Reference version:** RouterOS 7.x (sniffer availability depends on device-mode).

> ⚠️ Captures and debugging may consume resources or expose sensitive data. Use only on authorized networks, scope carefully and always stop afterward.

## /tool sniffer quick filter-interface=ether1 filter-ip-address=192.0.2.10

```text
/tool sniffer quick filter-interface=ether1 filter-ip-address=192.0.2.10
```

- **Purpose:** Live packet view for one interface and IP. Stop with Ctrl+C.
- **Parameters:** quick: live view; filter-interface: interface; filter-ip-address: matching IP.
- **Real-world use:** See whether traffic from the lab host crosses ether1.

## /tool sniffer quick filter-interface=ether1 filter-port=443

```text
/tool sniffer quick filter-interface=ether1 filter-port=443
```

- **Purpose:** Watch packets using TCP/UDP port 443.
- **Parameters:** filter-port: port match; quick: interactive capture.
- **Real-world use:** Find HTTPS flows without inspecting all packets.

## /tool sniffer set filter-interface=ether1 filter-ip-protocol=icmp file-name=lab-capture.pcap file-limit=1000KiB

```text
/tool sniffer set filter-interface=ether1 filter-ip-protocol=icmp file-name=lab-capture.pcap file-limit=1000KiB
/tool sniffer start
/tool sniffer stop
```

- **Purpose:** Save a bounded capture to a file for offline analysis.
- **Parameters:** file-name: capture file; file-limit: max size; stop: end capture.
- **Real-world use:** Inspect ICMP in Wireshark; check actual file format in your RouterOS version.

## /system device-mode print

```text
/system device-mode print
```

- **Purpose:** Check if sniffing is permitted by RouterOS device-mode.
- **Parameters:** print: feature state.
- **Real-world use:** Diagnose 'not allowed by device-mode' before changing anything.

**Vendor reference:** https://help.mikrotik.com/docs/spaces/ROS/pages/8323088/Packet%20Sniffer

**Note:** EPC/sniffer may not see hardware-offloaded packets. Protocol debugging is not the same as PCAP.
