---
tags: [cli, dell, field-queries]
validation: not-lab-verified
---

# Five additional operational queries — Dell OS10

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Index](README.md)

> Verify support on your exact model/release; examples pending lab tests.

## NTP peer status

```text
show ntp associations
```

- **Purpose:** NTP peer status.
- **Flags:** associations: NTP peers.
- **Practical use:** Focus on one operational symptom during investigation.

## Interface port health

```text
show interface ethernet 1/1/5 | grep error
```

- **Purpose:** Interface port health.
- **Flags:** ethernet 1/1/5: port identifier.
- **Practical use:** Focus on one operational symptom during investigation.

## Management VRF routes

```text
show ip route vrf management | grep 198.51.100
```

- **Purpose:** Management VRF routes.
- **Flags:** vrf management: specific routing instance.
- **Practical use:** Focus on one operational symptom during investigation.

## Spanning-tree topology

```text
show spanning-tree | grep Root
```

- **Purpose:** Spanning-tree topology.
- **Flags:** No flags; switching feature required.
- **Practical use:** Focus on one operational symptom during investigation.

## ARP neighbor inspection

```text
show arp | grep 192.0.2
```

- **Purpose:** ARP neighbor inspection.
- **Flags:** ARP cache: L3 neighbors.
- **Practical use:** Focus on one operational symptom during investigation.

