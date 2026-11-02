---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Comandos operativos — Huawei VRP

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** VRP (check device release). Verificar comandos en equipo real.

## `display lldp neighbor brief`

```text
display lldp neighbor brief | include GigabitEthernet
```

- **Sirve para:** Lista vecinos LLDP.
- **Parámetros:** brief: resumen
- **Filtro / consulta:** `display lldp neighbor brief | include GigabitEthernet`

## `display vlan`

```text
display vlan | include 10
```

- **Sirve para:** Muestra información de VLAN.
- **Parámetros:** Sin opciones
- **Filtro / consulta:** `display vlan | include 10`

## `display mac-address`

```text
display mac-address | include 0011-2233-4455
```

- **Sirve para:** Consulta tabla MAC.
- **Parámetros:** Sin opciones
- **Filtro / consulta:** `display mac-address | include 0011-2233-4455`

## `display stp brief`

```text
display stp brief | include DISCARDING
```

- **Sirve para:** Resume estado STP.
- **Parámetros:** brief: salida breve
- **Filtro / consulta:** `display stp brief | include DISCARDING`

## `display lldp local interface GigabitEthernet 0/0/1`

```text
display lldp local interface GigabitEthernet 0/0/1
```

- **Sirve para:** Consulta la información LLDP local anunciada en una interfaz específica.
- **Parámetros:** local: información LLDP local; interface: puerto seleccionado; GigabitEthernet 0/0/1: interfaz de ejemplo.
- **Ejemplo de uso:** Verificar LLDP en el uplink cuando otro switch no logra descubrirlo.
- **Referencia oficial:** https://info.support.huawei.com/network/ptmngsys/Web/tsrev_s/en/content/s/38_edesk_lldp_neighbors_failing/edesk_lldp_neighbors_failing_edesk002.html

## `display bgp peer | include Established`

```text
display bgp peer | include Established
```

- **Sirve para:** Muestra vecinos BGP cuyo estado aparezca como Established.
- **Parámetros:** display bgp peer: estado de peers; | include Established: mantiene líneas coincidentes.
- **Ejemplo de uso:** Comprobar adyacencias BGP establecidas tras un cambio de routing.
- **Referencia:** https://info.support.huawei.com/network/ptmngsys/Web/tsrev_ce/es/content/ce/18_edesk_dc_failed_to_forward_evpn_unicast_traffic/edesk_dc_failed_to_forward_evpn_unicast_traffic_edesk001.html

> Ejemplos pendientes de validación práctica. Confirma versión y sintaxis con la ayuda de CLI.
