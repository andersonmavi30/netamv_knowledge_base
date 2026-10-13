---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Comandos operativos — Huawei VRP

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** VRP (check device release). Verificar comandos en equipo real.

## `display lldp neighbor brief`

```text
display lldp neighbor brief
```

- **Sirve para:** Lista vecinos LLDP.
- **Parámetros:** brief: resumen
- **Filtro / consulta:** `display lldp neighbor brief | include GigabitEthernet`

## `display vlan`

```text
display vlan
```

- **Sirve para:** Muestra información de VLAN.
- **Parámetros:** Sin opciones
- **Filtro / consulta:** `display vlan | include 10`

## `display mac-address`

```text
display mac-address
```

- **Sirve para:** Consulta tabla MAC.
- **Parámetros:** Sin opciones
- **Filtro / consulta:** `display mac-address | include 0011-2233-4455`

## `display stp brief`

```text
display stp brief
```

- **Sirve para:** Resume estado STP.
- **Parámetros:** brief: salida breve
- **Filtro / consulta:** `display stp brief | include DISCARDING`

## `display ip routing-table 198.51.100.10`

```text
display ip routing-table 198.51.100.10
```

- **Sirve para:** Consulta ruta hacia destino.
- **Parámetros:** IP: destino
- **Filtro / consulta:** `display ip routing-table | include 198.51.100`

> Ejemplos pendientes de validación práctica. Confirma versión y sintaxis con la ayuda de CLI.
