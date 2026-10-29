---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Búsquedas de operación — Fortinet FortiOS

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Índice](README.es.md)

> Los ejemplos son orientativos: valida el modelo, release y ayuda de CLI antes de usarlos.

## Decisiones SD-WAN

```text
diagnose sys sdwan service | grep -i member
```

- **Sirve para:** Decisiones SD-WAN.
- **Opciones y filtros:** service: estado y selección
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Sesiones por IP origen

```text
diagnose sys session list | grep 192.0.2.10
```

- **Sirve para:** Sesiones por IP origen.
- **Opciones y filtros:** list: sesiones activas
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Resumen de vecinos BGP

```text
get router info bgp summary | grep 192.0.2
```

- **Sirve para:** Resumen de vecinos BGP.
- **Opciones y filtros:** summary: vecinos resumidos
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Contadores físicos de NIC

```text
diagnose hardware deviceinfo nic port1 | grep -i error
```

- **Sirve para:** Contadores físicos de NIC.
- **Opciones y filtros:** nic port1: interfaz
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## ARP de un host

Consulta el comando `get system arp | grep 192.0.2.10` en la [guía de consultas](01-show.es.md).

