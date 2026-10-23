---
tags: [cli, cisco-ios-classic, operations]
validation: not-lab-verified
---

# 📋 Comandos adicionales de operación

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ Índice](README.es.md)

**Familia de versiones:** 15.x. La disponibilidad depende de modelo, licencia y versión.

## `show ip ospf neighbor`

```text
show ip ospf neighbor | include FULL
```

- **Sirve para:** Muestra vecinos OSPF.
- **Parámetros:** Sin argumentos.
- **Caso real:** Buscar vecinos en FULL.
- **Filtro/validación:** `show ip ospf neighbor | include FULL`

## `show ip protocols`

```text
show ip protocols | include Routing Protocol
```

- **Sirve para:** Consulta protocolos de routing.
- **Parámetros:** Sin argumentos.
- **Caso real:** Revisar redes configuradas.
- **Filtro/validación:** `show ip protocols | include Routing Protocol`

## `show access-lists`

```text
show access-lists 101
```

- **Sirve para:** Muestra ACL y contadores.
- **Parámetros:** Sin argumentos.
- **Caso real:** Localizar reglas ACL 101.
- **Filtro/validación:** `show access-lists 101`

## `show cdp neighbors detail`

```text
show cdp neighbors detail | include Device ID
```

- **Sirve para:** Muestra detalles de vecinos Cisco.
- **Parámetros:** detail: añade datos e IP.
- **Caso real:** Encontrar vecino del enlace.
- **Filtro/validación:** `show cdp neighbors detail | include Device ID|IP address`

## `show ip arp`

```text
show ip arp | include 192.0.2.10
```

- **Sirve para:** Muestra mapeo IPv4 a MAC.
- **Parámetros:** Sin argumentos.
- **Caso real:** Buscar MAC de host.
- **Filtro/validación:** `show ip arp | include 192.0.2.10`

## `show interfaces status`

```text
show interfaces status | include notconnect
```

- **Sirve para:** Muestra estado de puertos (switches compatibles).
- **Parámetros:** status: resumen; depende del equipo.
- **Caso real:** Encontrar puertos deshabilitados.
- **Filtro/validación:** `show interfaces status | include notconnect|err-disabled`

## `show spanning-tree`

```text
show spanning-tree | include BLK
```

- **Sirve para:** Consulta STP en plataformas L2.
- **Parámetros:** Sin argumentos; requiere STP.
- **Caso real:** Encontrar puertos bloqueados.
- **Filtro/validación:** `show spanning-tree | include BLK`

## `show vlan brief`

```text
show vlan brief | include 10
```

- **Sirve para:** Lista VLAN de switches compatibles.
- **Parámetros:** brief: resumen.
- **Caso real:** Buscar VLAN 10.
- **Filtro/validación:** `show vlan brief | include 10`

> No probado en laboratorio; verificar con la ayuda CLI y documentación de la versión antes de ejecutarlo. Los respaldos completos y las salidas de diagnóstico pueden contener datos sensibles.
