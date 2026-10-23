---
tags: [cli, dell, os10, troubleshooting]
validation: not-lab-verified
---

# Diagnóstico — Dell OS10

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** Dell SmartFabric OS10 (PowerSwitch hardware/release dependent). Verifica con `show version` y `?`.

## `show logging`

```text
show logging | grep DOWN
```

- **Sirve para:** Consulta eventos.
- **Parámetros:** Sin opciones.
- **Caso real:** Investigar flapping.

## `show interface ethernet 1/1/1`

```text
show interface ethernet 1/1/1
```

- **Sirve para:** Consulta interfaz física.
- **Parámetros:** 1/1/1: nodo/slot/puerto.
- **Caso real:** Buscar descartes.

## `show mac address-table`

```text
show mac address-table
```

- **Sirve para:** Consulta tabla L2 en versiones compatibles.
- **Parámetros:** Sin opciones.
- **Caso real:** Ubicar MAC aprendida.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://www.dell.com/support/manuals/en-us/dell-emc-smartfabric-os10/smartfabric-os-user-guide-10-5-0/Filter-show-commands?guid=guid-758c857a-eba2-477a-a8f5-f0738c185e54&lang=en-us)
