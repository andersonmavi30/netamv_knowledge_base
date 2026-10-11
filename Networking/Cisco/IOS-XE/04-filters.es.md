---
tags: [cli, cisco, ios-xe, filters]
vendor: Cisco
os: "IOS XE"
validation: not-lab-verified
---

# 🔍 Filtros de salida

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Cisco](../README.es.md)

**Plataforma:** Cisco / IOS XE · **Compatibilidad:** Cisco IOS XE 17.x (depende del modelo; valida tu versión).

## `show ip interface brief | include GigabitEthernet`

```text
show ip interface brief | include GigabitEthernet
```

- **Sirve para:** Muestra solamente interfaces coincidentes.
- **Parámetros:** |: tubería; include: líneas coincidentes.
- **Ejemplo de uso:** Consultar estado de GigabitEthernet.

- **Filtro práctico:** `show ip interface brief | include GigabitEthernet1/0/1` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.

## `show logging | exclude LINK`

```text
show logging | exclude LINK
```

- **Sirve para:** Oculta líneas de logs que incluyan LINK.
- **Parámetros:** exclude: elimina líneas coincidentes.
- **Ejemplo de uso:** Centrarse en otros registros.

- **Filtro práctico:** `show logging | include LINK|LINEPROTO` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.

## `show running-config | section interface`

```text
show running-config | section interface
```

- **Sirve para:** Muestra secciones de configuración de interfaces.
- **Parámetros:** section: incluye bloques de configuración coincidentes.
- **Ejemplo de uso:** Consultar configuración de varias interfaces.

- **Filtro práctico:** `show running-config | section ^interface GigabitEthernet1/0/1` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.

## `show running-config | begin interface`

```text
show running-config | begin interface
```

- **Sirve para:** Muestra salida desde la primera coincidencia de interface.
- **Parámetros:** begin: inicia en la primera coincidencia (no filtra un bloque exacto).
- **Ejemplo de uso:** Saltar la cabecera de la configuración.

- **Filtro práctico:** `show ip route 198.51.100.10` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.


> **Nota:** Referencia rápida, no verificada en laboratorio; confirma sintaxis y permisos en tu modelo y versión.

**Fuente del fabricante:** https://www.cisco.com/c/en/us/td/docs/routers/access/isr1100/software/configuration/xe-17/isr1100-sw-config-xe-17/using_iosxe_software.pdf
