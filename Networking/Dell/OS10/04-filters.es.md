---
tags: [dell, os10, cli]
validation: not-lab-verified
---

# Filtros — Dell OS10

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell SmartFabric OS10 — supported PowerSwitch platforms; verify release/model.

## `show running-configuration`

```text
show running-configuration
```

- **Sirve para:** Consulta configuración antes de filtros particulares.
- **Parámetros:** Verifica pipe y regex con ayuda CLI.
- **Caso práctico:** Localizar interfaz.
- **Verificación:** `show running-configuration`

## `show ip route`

```text
show ip route
```

- **Sirve para:** Consulta rutas; filtra tras validar sintaxis.
- **Parámetros:** OS10 no es idéntico a Cisco IOS.
- **Caso práctico:** Revisar ruta destino.
- **Verificación:** `show ip route`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
