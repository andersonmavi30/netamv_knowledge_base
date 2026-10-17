---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Comandos operativos — Cisco IOS XE

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** IOS XE (check release). Verificar comandos en equipo real.

## `show ip ospf interface brief`

```text
show ip ospf interface brief
```

- **Sirve para:** Muestra interfaces OSPF.
- **Parámetros:** brief: resumen
- **Filtro / consulta:** `show ip ospf interface brief | include GigabitEthernet`

## `show ip route ospf`

```text
show ip route ospf
```

- **Sirve para:** Muestra rutas OSPF.
- **Parámetros:** ospf: protocolo de routing
- **Filtro / consulta:** `show ip route ospf | include 198.51.100`

## `show access-lists 101`

```text
show access-lists 101
```

- **Sirve para:** Consulta ACL 101.
- **Parámetros:** 101: ID ACL
- **Filtro / consulta:** `show access-lists 101 | include deny`



> Ejemplos pendientes de validación práctica. Confirma versión y sintaxis con la ayuda de CLI.
