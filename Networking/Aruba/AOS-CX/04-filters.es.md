---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Filtros de salida

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** AOS-CX 10.x; comprueba versión y sintaxis con `show version` y `?`.

## `show running-config | include hostname`

```text
show running-config | include hostname
```

- **Sirve para:** Encuentra hostname.
- **Parámetros:** include: conserva coincidencias.
- **Ejemplo de uso:** Identificar switch.

## `show running-config | exclude description`

```text
show running-config | exclude description
```

- **Sirve para:** Oculta líneas description.
- **Parámetros:** exclude: elimina coincidencias.
- **Ejemplo de uso:** Revisar configuración.

## `show running-config | begin vlan`

```text
show running-config | begin vlan
```

- **Sirve para:** Inicia salida desde VLAN.
- **Parámetros:** begin: inicia en coincidencia.
- **Ejemplo de uso:** Revisar bloques VLAN.

## `show interface brief | include down | count`

```text
show interface brief | include down | count
```

- **Sirve para:** Cuenta líneas coincidentes con down.
- **Parámetros:** count: líneas filtradas.
- **Ejemplo de uso:** Estimar puertos caídos.

> Ejemplos pendientes de validación en laboratorio; comandos y filtros pueden variar según versión y equipo.
