---
tags: [dell, os10, cli]
validation: not-lab-verified
---

# Consultas y estado — Dell OS10

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell SmartFabric OS10 — supported PowerSwitch platforms; verify release/model.

## `show version`

```text
show version
```

- **Sirve para:** Identifica versión OS10.
- **Parámetros:** Sin parámetros.
- **Caso práctico:** Comprobar versión.
- **Verificación:** `show version`

## `show interface status`

```text
show interface status
```

- **Sirve para:** Resume interfaces; validar en tu versión.
- **Parámetros:** status: resumen.
- **Caso práctico:** Buscar enlaces down.
- **Verificación:** `show interface status`

## `show ip route`

```text
show ip route
```

- **Sirve para:** Muestra rutas.
- **Parámetros:** Sin parámetros.
- **Caso práctico:** Buscar prefijos.
- **Verificación:** `show ip route`

## `show vlan`

```text
show vlan
```

- **Sirve para:** Consulta VLAN.
- **Parámetros:** Sin parámetros.
- **Caso práctico:** Revisar VLAN.
- **Verificación:** `show vlan`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
