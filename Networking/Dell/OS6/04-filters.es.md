---
tags: [cli, dell, os6, filters]
validation: not-lab-verified
---

# Filtros de salida — Dell OS6

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** OS6 / N-Series; CLI output filtering is available in OS6 6.6+ where supported. Verifica con `show version` y `?`.

## `show running-config | include hostname`

```text
show running-config | include hostname
```

- **Sirve para:** Busca solo el hostname.
- **Parámetros:** | include: líneas coincidentes.
- **Caso real:** Identificar switch.

## `show running-config | section interface`

```text
show running-config | section interface
```

- **Sirve para:** Busca secciones de interfaces.
- **Parámetros:** | section: bloque coincidente.
- **Caso real:** Revisar configuraciones.

## `show interfaces status | include 1/0/1`

```text
show interfaces status | include 1/0/1
```

- **Sirve para:** Busca puerto en listado.
- **Parámetros:** | include: busca texto.
- **Caso real:** Ver uplink.

## `show logging | exclude LINK`

```text
show logging | exclude LINK
```

- **Sirve para:** Oculta mensajes de enlace repetidos.
- **Parámetros:** | exclude: omite coincidencias.
- **Caso real:** Revisar otras alarmas.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)
