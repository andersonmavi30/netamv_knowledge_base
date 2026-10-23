---
tags: [cli, fortinet, fortios, show]
vendor: Fortinet
os: "FortiOS"
validation: not-lab-verified
---

# 🔎 Consultas y estado

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Fortinet](../README.es.md)

**Plataforma:** Fortinet / FortiOS · **Compatibilidad:** FortiOS 7.x (comprueba tu versión exacta).

## `get system status`

```text
get system status | grep -i hostname
```

- **Sirve para:** Muestra hostname, firmware e identificadores del sistema.
- **Parámetros:** Sin parámetros.
- **Ejemplo de uso:** Identificar firmware antes de diagnosticar.

- **Filtro práctico:** `get system status | grep -i hostname` — Ubica rápidamente el hostname.

## `get system performance status`

```text
get system performance status | grep -i cpu
```

- **Sirve para:** Consulta CPU, memoria, uptime y estadísticas de sesiones.
- **Parámetros:** Sin parámetros.
- **Ejemplo de uso:** Revisión rápida de salud.

- **Filtro práctico:** `get system performance status | grep -i cpu` — Filtra líneas relacionadas con CPU.

## `get system interface`

```text
get system interface | grep -i port3
```

- **Sirve para:** Lista estado y direccionamiento de interfaces.
- **Parámetros:** Sin parámetros.
- **Ejemplo de uso:** Consultar la IP de una interfaz.

- **Filtro práctico:** `get system interface | grep -i port3` — Encuentra port3; para ver todas sus propiedades consulta la salida completa.

## `get router info routing-table all`

```text
get router info routing-table all | grep 198.51.100
```

- **Sirve para:** Muestra la tabla de enrutamiento.
- **Parámetros:** all: muestra rutas de varios protocolos.
- **Ejemplo de uso:** Validar el siguiente salto hacia una red.

- **Filtro práctico:** `get router info routing-table all | grep 198.51.100` — Busca un prefijo; filtrar texto no equivale a consultar la ruta efectiva.


> **Nota:** Referencia rápida, no verificada en laboratorio; confirma sintaxis y permisos en tu modelo y versión.

**Fuente del fabricante:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966
