---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Búsquedas de operación — Huawei VRP

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Índice](README.es.md)

> Los ejemplos son orientativos: valida el modelo, release y ayuda de CLI antes de usarlos.

## Descripciones de interfaces

Consulta el comando y su filtro en la [guía de interfaces](03-interfaces.es.md).

## Estado NTP

```text
display ntp-service status
```

- **Sirve para:** Estado NTP.
- **Opciones y filtros:** status: sincronización
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Interfaces con OSPF

```text
display ospf interface | include GigabitEthernet
```

- **Sirve para:** Interfaces con OSPF.
- **Opciones y filtros:** interface: puertos participantes
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Estado Eth-Trunk

```text
display eth-trunk 1
```

- **Sirve para:** Estado Eth-Trunk.
- **Opciones y filtros:** 1: índice trunk
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Diagnóstico de óptico

```text
display transceiver interface GigabitEthernet0/0/1 verbose
```

- **Sirve para:** Diagnóstico de óptico.
- **Opciones y filtros:** verbose: óptica detallada; según versión
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

