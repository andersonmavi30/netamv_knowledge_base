---
tags: [cli, fortinet, fortios, show]
vendor: Fortinet
os: "FortiOS"
validation: not-lab-verified
---

# 🔎 Consultas y estado

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Fortinet](../README.es.md)

**Plataforma:** Fortinet / FortiOS · **Compatibilidad:** FortiOS 7.4 (ejemplos; valida tu versión).

## `get system status`

```text
get system status
```

- **Sirve para:** Muestra hostname, firmware e identificadores del sistema.
- **Parámetros:** Sin parámetros.
- **Ejemplo de uso:** Identificar firmware antes de diagnosticar.

## `get system performance status`

```text
get system performance status
```

- **Sirve para:** Consulta CPU, memoria, uptime y estadísticas de sesiones.
- **Parámetros:** Sin parámetros.
- **Ejemplo de uso:** Revisión rápida de salud.

## `get system interface`

```text
get system interface
```

- **Sirve para:** Lista estado y direccionamiento de interfaces.
- **Parámetros:** Sin parámetros.
- **Ejemplo de uso:** Consultar la IP de una interfaz.

## `get router info routing-table all`

```text
get router info routing-table all
```

- **Sirve para:** Muestra la tabla de enrutamiento.
- **Parámetros:** all: muestra rutas de varios protocolos.
- **Ejemplo de uso:** Validar el siguiente salto hacia una red.

> **Nota:** Referencia rápida, no verificada en laboratorio; confirma sintaxis y permisos en tu modelo y versión.

**Fuente del fabricante:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966
