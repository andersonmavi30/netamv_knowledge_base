---
tags: [dell, os9, cli]
validation: not-lab-verified
---

# Filtros — Dell OS9

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell Networking OS9 / FTOS — Force10-derived platforms, model-dependent.

## `show interfaces`

```text
show interfaces
```

- **Sirve para:** Consulta salida antes de usar filtros específicos.
- **Parámetros:** Pipe varía entre versiones; verifica con ?.
- **Caso práctico:** Buscar datos operativos.
- **Verificación:** `show interfaces`

## `show ip route`

```text
show ip route
```

- **Sirve para:** Consulta rutas antes de filtrar.
- **Parámetros:** Usa ayuda CLI para sintaxis.
- **Caso práctico:** Buscar redes destino.
- **Verificación:** `show ip route`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
