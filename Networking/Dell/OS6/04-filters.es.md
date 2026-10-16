---
tags: [dell, os6, cli]
validation: not-lab-verified
---

# Filtros — Dell OS6

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell Networking OS6 — generally N-series (check model/release).

## `show running-config`

```text
show running-config
```

- **Sirve para:** Revisa configuración; confirma si admite filtros pipe.
- **Parámetros:** Filtros varían entre revisiones.
- **Caso práctico:** Buscar ajustes de puerto.
- **Verificación:** `show running-config`

## `show logging`

```text
show logging
```

- **Sirve para:** Consulta eventos antes de filtrar.
- **Parámetros:** Consulta ? para filtros disponibles.
- **Caso práctico:** Investigar flapping.
- **Verificación:** `show logging`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
