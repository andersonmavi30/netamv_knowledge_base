---
tags: [cli, dell, os10, filters]
validation: not-lab-verified
---

# Filtros de salida — Dell OS10

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** Dell SmartFabric OS10 (PowerSwitch hardware/release dependent). Verifica con `show version` y `?`.

## `show running-configuration | grep hostname`

```text
show running-configuration | grep hostname
```

- **Sirve para:** Encuentra hostname.
- **Parámetros:** | grep: coincidencias.
- **Caso real:** Identificar equipo.

## `show interface status | grep down`

```text
show interface status | grep down
```

- **Sirve para:** Filtra interfaces caídas.
- **Parámetros:** | grep: patrón de texto.
- **Caso real:** Ubicar fallas de enlace.

## `show ip route | grep 198.51.100`

```text
show ip route | grep 198.51.100
```

- **Sirve para:** Buscar prefijo.
- **Parámetros:** | grep: texto, no lookup.
- **Caso real:** Encontrar prefijo.

## `show running-configuration | except description`

```text
show running-configuration | except description
```

- **Sirve para:** Oculta líneas description.
- **Parámetros:** | except: omite coincidencias.
- **Caso real:** Revisar configuración.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://www.dell.com/support/manuals/en-us/dell-emc-smartfabric-os10/smartfabric-os-user-guide-10-5-0/Filter-show-commands?guid=guid-758c857a-eba2-477a-a8f5-f0738c185e54&lang=en-us)
