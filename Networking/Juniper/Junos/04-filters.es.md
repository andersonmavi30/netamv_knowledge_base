---
tags: [cli, juniper, junos]
validation: not-lab-verified
---

# Filtros de salida

[English](04-filters.md) · [Español](04-filters.es.md) · [Índice](README.es.md)

**Compatibilidad:** Junos OS; verificar modelo, versión y `?`.

## `show log messages | match "error"`

```text
show log messages | match "error"
```

- **Sirve para:** Filtrar logs del sistema por líneas con error.
- **Parámetros:** match: filtro regex de salida Junos; "error": patrón sensible a mayúsculas.
- **Ejemplo de uso:** Encontrar errores del sistema durante el diagnóstico.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/filtering-operational-command.html

> Pendiente de validación en laboratorio.
