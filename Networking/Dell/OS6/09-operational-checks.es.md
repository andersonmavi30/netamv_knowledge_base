---
tags: [cli, networking, operational-checks]
validation: not-lab-verified
---

# Verificaciones operativas adicionales — Dell OS6

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** OS6 — N-series, release-specific. Confirma comando y flags con la ayuda contextual de tu versión.

## Vecinos LLDP

```text
show lldp neighbors
```

- **Sirve para:** Muestra equipos vecinos.
- **Parámetros / flags:** neighbors: vecinos LLDP.
- **Caso real:** Identificar equipo conectado.
- **Filtro / verificación:** `show lldp neighbors`

## Tabla ARP IPv4

```text
show ip arp
```

- **Sirve para:** Muestra entradas IP-MAC con L3.
- **Parámetros / flags:** Sin parámetros; requiere L3.
- **Caso real:** Buscar MAC del gateway.
- **Filtro / verificación:** `show ip arp`

## Estado MST

```text
show spanning-tree mst
```

- **Sirve para:** Consulta información de MST.
- **Parámetros / flags:** mst: múltiples instancias STP.
- **Caso real:** Investigar enlaces bloqueados.
- **Filtro / verificación:** `show spanning-tree mst`

## Detalles de switchport

```text
show interfaces switchport gigabitethernet 1/0/1
```

- **Sirve para:** Revisa VLAN permitidas y modo access/trunk.
- **Parámetros / flags:** La interfaz depende del modelo.
- **Caso real:** Revisar inconsistencia VLAN.
- **Filtro / verificación:** `show interfaces switchport gigabitethernet 1/0/1`

## Tabla DHCP snooping

```text
show ip dhcp snooping binding
```

- **Sirve para:** Consulta bindings DHCP snooping si está activo.
- **Parámetros / flags:** binding: asociaciones DHCP.
- **Caso real:** Investigar cliente DHCP bloqueado.
- **Filtro / verificación:** `show ip dhcp snooping binding`

> ⚠️ Referencia de laboratorio aún no probada; distintas plataformas Dell y Huawei pueden usar variantes de comandos.

[Referencia del fabricante](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)
