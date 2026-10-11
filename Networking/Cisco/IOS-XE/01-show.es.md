---
tags: [cli, cisco, ios-xe, show]
vendor: Cisco
os: "IOS XE"
validation: not-lab-verified
---

# 🔎 Consultas y estado

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Cisco](../README.es.md)

**Plataforma:** Cisco / IOS XE · **Compatibilidad:** Cisco IOS XE 17.x (depende del modelo; valida tu versión).

## `show version`

```text
show version
```

- **Sirve para:** Muestra versión de IOS XE, uptime y datos de hardware.
- **Parámetros:** Sin parámetros.
- **Ejemplo de uso:** Identificar la versión instalada.

- **Filtro práctico:** `show version | include IOS|uptime` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.

## `show ip interface brief`

```text
show ip interface brief
```

- **Sirve para:** Resume IP y estado de interfaces IPv4.
- **Parámetros:** brief: salida resumida.
- **Ejemplo de uso:** Detectar una interfaz administrativamente apagada.

- **Filtro práctico:** `show ip interface brief | include GigabitEthernet` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.

## `show ip route`

```text
show ip route
```

- **Sirve para:** Muestra la tabla de enrutamiento IPv4.
- **Parámetros:** Sin parámetros.
- **Ejemplo de uso:** Revisar rutas instaladas.

- **Filtro práctico:** `show ip route 198.51.100.10` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.

## `show interfaces GigabitEthernet1/0/1`

```text
show interfaces GigabitEthernet1/0/1
```

- **Sirve para:** Consulta estado de enlace, tráfico y contadores de errores.
- **Parámetros:** El nombre de la interfaz depende del modelo.
- **Ejemplo de uso:** Investigar errores CRC o descartes.

- **Filtro práctico:** `show interfaces GigabitEthernet1/0/1 | include line protocol|errors|drops` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.


> **Nota:** Referencia rápida, no verificada en laboratorio; confirma sintaxis y permisos en tu modelo y versión.

**Fuente del fabricante:** https://www.cisco.com/c/en/us/td/docs/routers/access/isr1100/software/configuration/xe-17/isr1100-sw-config-xe-17/using_iosxe_software.pdf
