---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Consultas de campo

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** AOS-CX 10.x; validar por modelo y release.

## `show lacp aggregates | include lag1`

```text
show lacp aggregates | include lag1
```

- **Sirve para:** Revisa agregación LACP.
- **Parámetros:** include: nombre LAG.
- **Ejemplo de uso:** Diagnosticar LAG.

## `show ntp associations | include 192.0.2`

```text
show ntp associations | include 192.0.2
```

- **Sirve para:** Busca asociaciones NTP.
- **Parámetros:** include: patrón IP.
- **Ejemplo de uso:** Revisar peers.

## `show interface 1/1/4 | include error`

```text
show interface 1/1/4 | include error
```

- **Sirve para:** Consulta errores del puerto.
- **Parámetros:** include: palabra error.
- **Ejemplo de uso:** Buscar fallas.

## `show ip route | include 203.0.113`

```text
show ip route | include 203.0.113
```

- **Sirve para:** Busca prefijo en rutas.
- **Parámetros:** include: busca prefijo.
- **Ejemplo de uso:** Revisar ruta.

> Validar en laboratorio. Mirror/tshark requieren soporte y autorización; deshabilita al finalizar.
