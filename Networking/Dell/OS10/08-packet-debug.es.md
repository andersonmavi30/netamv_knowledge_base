---
tags: [dell, os10, cli]
validation: not-lab-verified
---

# Diagnóstico de paquetes — Dell OS10

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell SmartFabric OS10 — supported PowerSwitch platforms; verify release/model.

## `show interface`

```text
show interface
```

- **Sirve para:** Revisa errores de puerto antes de capturar.
- **Parámetros:** La sintaxis por puerto varía.
- **Caso práctico:** Determinar descartes.
- **Verificación:** `show interface`

## `show logging`

```text
show logging
```

- **Sirve para:** Consulta eventos; no es captura de paquetes.
- **Parámetros:** Confirmar logging CLI según versión.
- **Caso práctico:** Encontrar horario de falla.
- **Verificación:** `show logging`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
