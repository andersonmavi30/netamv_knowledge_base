---
tags: [cli, packet-capture, debugging]
validation: not-lab-verified
---

# 🧪 Packet capture & debugging — Huawei VRP

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Index](README.md)

**Reference version:** VRP generic (verify product/release).

> ⚠️ Captures and debugging may consume resources or expose sensitive data. Use only on authorized networks, scope carefully and always stop afterward.

## debugging ospf packet hello interface GigabitEthernet1/0/0

```text
debugging ospf packet hello interface GigabitEthernet1/0/0
terminal monitor
terminal debugging
```

- **Purpose:** Temporarily observe OSPF Hello packets and terminal debugging on supported VRP platforms.
- **Parameters:** hello: Hello packets; interface: limits scope; terminal debugging: display debug output.
- **Real-world use:** Inspect why OSPF neighbors do not become FULL.

## undo debugging ospf packet

```text
undo debugging ospf packet
undo terminal debugging
undo terminal monitor
```

- **Purpose:** Turn OSPF packet debug and terminal tracing off.
- **Parameters:** undo: reverse the corresponding debug/monitor setting.
- **Real-world use:** Avoid leaving high-volume debugging enabled.

## display logbuffer | include DOWN

```text
display logbuffer | include DOWN
```

- **Purpose:** Search control-plane log events; this does not capture full packets.
- **Parameters:** include: text matching lines, not raw packet data.
- **Real-world use:** Check interface down alarms before choosing a supported port-mirroring method.

**Vendor reference:** https://info.support.huawei.com/network/ptmngsys/Web/tsrev_ne/en/content/ne/21_edesk_ne_ospf_peer_status_is_abnormal/edesk_ne_ospf_peer_status_is_abnormal_edesk002.html

**Note:** EPC/sniffer may not see hardware-offloaded packets. Protocol debugging is not the same as PCAP.
