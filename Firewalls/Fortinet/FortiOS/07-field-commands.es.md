---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Comandos operativos — Fortinet FortiOS

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** FortiOS 7.x. Verificar comandos en equipo real.

## `get system ha status`

```text
get system ha status
```

- **Sirve para:** Consulta clúster HA.
- **Parámetros:** Sin flags
- **Filtro / consulta:** `get system ha status | grep -i mode`

## `diagnose sys session stat`

```text
diagnose sys session stat
```

- **Sirve para:** Consulta estadísticas de sesiones.
- **Parámetros:** stat: cuentas de sesiones
- **Filtro / consulta:** `diagnose sys session stat | grep -i session`

## `diagnose vpn ike gateway list`

```text
diagnose vpn ike gateway list
```

- **Sirve para:** Consulta gateways IKE.
- **Parámetros:** list: gateways
- **Filtro / consulta:** `diagnose vpn ike gateway list | grep -i name=`

## `get router info routing-table all`

```text
get router info routing-table all
```

- **Sirve para:** Consulta rutas actuales.
- **Parámetros:** all: tabla completa
- **Filtro / consulta:** `get router info routing-table all | grep 198.51.100`

## `show firewall address`

```text
show firewall address
```

- **Sirve para:** Consulta objetos address.
- **Parámetros:** Sin flags
- **Filtro / consulta:** `show firewall address | grep -f LAB-NET`

> Ejemplos pendientes de validación práctica. Confirma versión y sintaxis con la ayuda de CLI.
