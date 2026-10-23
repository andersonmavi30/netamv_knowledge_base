---
tags: [cli, dell, field-queries]
validation: not-lab-verified
---

# Five additional operational queries — Dell OS9

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Index](README.md)

> Verify support on your exact model/release; examples pending lab tests.

## BGP route inspection

```text
show ip route bgp | grep 198.51.100
```

- **Purpose:** BGP route inspection.
- **Flags:** bgp: limit table to BGP routes.
- **Practical use:** Focus on one operational symptom during investigation.

## Detailed physical port counters

```text
show interfaces tengigabitethernet 0/2 | grep error
```

- **Purpose:** Detailed physical port counters.
- **Flags:** 0/2: target port; model-dependent.
- **Practical use:** Focus on one operational symptom during investigation.

## Specific interface running settings

```text
show running-config interface tengigabitethernet 0/2
```

- **Purpose:** Specific interface running settings.
- **Flags:** interface: specific port.
- **Practical use:** Focus on one operational symptom during investigation.

## Clock synchronization check

```text
show ntp status
```

- **Purpose:** Clock synchronization check.
- **Flags:** status: NTP state; platform-dependent.
- **Practical use:** Focus on one operational symptom during investigation.

## Focused uptime search

```text
show version | grep uptime
```

- **Purpose:** Focused uptime search.
- **Flags:** grep: output match.
- **Practical use:** Focus on one operational symptom during investigation.

