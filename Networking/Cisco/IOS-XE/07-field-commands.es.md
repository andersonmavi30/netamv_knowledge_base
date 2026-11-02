---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Comandos operativos — Cisco IOS XE

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** IOS XE (check release). Verificar comandos en equipo real.

## `show ip ospf interface brief`

```text
show ip ospf interface brief | include GigabitEthernet
```

- **Sirve para:** Muestra interfaces OSPF.
- **Parámetros:** brief: resumen
- **Filtro / consulta:** `show ip ospf interface brief | include GigabitEthernet`

## `show ip route ospf`

```text
show ip route ospf | include 198.51.100
```

- **Sirve para:** Muestra rutas OSPF.
- **Parámetros:** ospf: protocolo de routing
- **Filtro / consulta:** `show ip route ospf | include 198.51.100`

## `show access-lists 101`

```text
show access-lists 101 | include deny
```

- **Sirve para:** Consulta ACL 101.
- **Parámetros:** 101: ID ACL
- **Filtro / consulta:** `show access-lists 101 | include deny`

## `show interfaces GigabitEthernet1/0/1 counters errors`

```text
show interfaces GigabitEthernet1/0/1 counters errors
```

- **Sirve para:** Muestra contadores de errores de un puerto sin listar todas las interfaces.
- **Parámetros:** GigabitEthernet1/0/1: identificador de interfaz; counters errors: vista de contadores de error.
- **Ejemplo de uso:** Buscar incrementos de FCS/errores de recepción en un uplink; requiere Catalyst IOS XE compatible.
- **Referencia oficial:** https://www.cisco.com/c/en/us/td/docs/switches/lan/catalyst9300/software/release/17-15/command_reference/b_1715_9300_cr/interface_and_hardware_commands.html

## `show ip sla statistics 1 | include Latest RTT|return code`

```text
show ip sla statistics 1 | include Latest RTT|return code
```

- **Sirve para:** Consulta el RTT y código de respuesta de IP SLA operación 1.
- **Parámetros:** statistics 1: operación SLA específica; | include: filtra RTT y código.
- **Ejemplo de uso:** Verificar latencia o errores en una sonda de conectividad.
- **Referencia:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/ipsla/command/sla-cr-book/sla_s1.html

> Ejemplos pendientes de validación práctica. Confirma versión y sintaxis con la ayuda de CLI.
