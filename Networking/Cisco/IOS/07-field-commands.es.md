---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Comandos operativos — Cisco IOS

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** IOS classic (check release). Verificar comandos en equipo real.

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
- **Parámetros:** ospf: origen de rutas
- **Filtro / consulta:** `show ip route ospf | include 198.51.100`

## `show access-lists 101`

```text
show access-lists 101 | include deny
```

- **Sirve para:** Consulta ACL 101.
- **Parámetros:** 101: ID ACL
- **Filtro / consulta:** `show access-lists 101 | include deny`

## `show ip route connected | include 192.0.2`

```text
show ip route connected | include 192.0.2
```

- **Sirve para:** Filtra las rutas directamente conectadas que contienen el prefijo 192.0.2.
- **Parámetros:** connected: rutas de interfaces locales; | include: muestra líneas que contienen el prefijo.
- **Ejemplo de uso:** Comprobar si la subred LAN del laboratorio está instalada como conectada.
- **Referencia oficial:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_pi/configuration/15-mt/iri-15-mt-book/iri-iprouting.html

> Ejemplos pendientes de validación práctica. Confirma versión y sintaxis con la ayuda de CLI.
