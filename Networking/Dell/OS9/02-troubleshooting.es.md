---
tags: [dell, os9, cli]
validation: not-lab-verified
---

# Diagnóstico — Dell OS9

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell Networking OS9 / FTOS — Force10-derived platforms, model-dependent.

## `show interfaces`

```text
show interfaces
```

- **Sirve para:** Revisa errores y enlace.
- **Parámetros:** Salida varía según puerto.
- **Caso práctico:** Investigar descartes.
- **Verificación:** `show interfaces`

## `show logging`

```text
show logging
```

- **Sirve para:** Consulta eventos del sistema.
- **Parámetros:** Sin parámetros.
- **Caso práctico:** Buscar transiciones de puerto.
- **Verificación:** `show logging`

## `show ip route`

```text
show ip route
```

- **Sirve para:** Revisa rutas instaladas.
- **Parámetros:** Sin parámetros.
- **Caso práctico:** Encontrar ruta faltante.
- **Verificación:** `show ip route`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
