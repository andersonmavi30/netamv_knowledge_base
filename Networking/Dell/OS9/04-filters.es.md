---
tags: [cli, dell, os9, filters]
validation: not-lab-verified
---

# Filtros de salida — Dell OS9

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** Dell Networking OS9 / Force10; confirm the platform and FTOS-derived CLI. Verifica con `show version` y `?`.

## `show running-config | grep hostname`

```text
show running-config | grep hostname
```

- **Sirve para:** Filtra hostname de la configuración.
- **Parámetros:** | grep: coincidencias.
- **Caso real:** Identificar switch.

## `show interfaces | grep error`

```text
show interfaces | grep error
```

- **Sirve para:** Muestra líneas con errores.
- **Parámetros:** | grep: sensible a mayúsculas.
- **Caso real:** Encontrar fallas.

## `show ip route | grep 198.51.100`

```text
show ip route | grep 198.51.100
```

- **Sirve para:** Busca prefijo en tabla.
- **Parámetros:** | grep: texto, no consulta de ruta.
- **Caso real:** Ubicar prefijo.

## `show logging | except INFO`

```text
show logging | except INFO
```

- **Sirve para:** Oculta líneas INFO.
- **Parámetros:** | except: elimina coincidencias.
- **Caso real:** Revisar eventos críticos.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://i.dell.com/sites/doccontent/shared-content/data-sheets/en/Documents/ESG-Dell-Force10-FTOS-CLI-Spec-Sheet.pdf)
