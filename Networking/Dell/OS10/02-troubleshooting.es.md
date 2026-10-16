---
tags: [dell, os10, cli]
validation: not-lab-verified
---

# Diagnóstico — Dell OS10

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell SmartFabric OS10 — supported PowerSwitch platforms; verify release/model.

## `show interface`

```text
show interface
```

- **Sirve para:** Consulta interfaces.
- **Parámetros:** Añade identificador según modelo.
- **Caso práctico:** Buscar errores uplink.
- **Verificación:** `show interface`

## `show logging`

```text
show logging
```

- **Sirve para:** Consulta eventos de OS10 donde aplique.
- **Parámetros:** Variaciones por versión.
- **Caso práctico:** Investigar flapping.
- **Verificación:** `show logging`

## `show ip route`

```text
show ip route
```

- **Sirve para:** Revisa tabla de rutas.
- **Parámetros:** Sin parámetros.
- **Caso práctico:** Confirmar ruta.
- **Verificación:** `show ip route`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
