---
tags: [dell, os9, cli]
validation: not-lab-verified
---

# Consultas y estado — Dell OS9

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell Networking OS9 / FTOS — Force10-derived platforms, model-dependent.

## `show version`

```text
show version
```

- **Sirve para:** Muestra versión OS9 y sistema.
- **Parámetros:** Sin parámetros.
- **Caso práctico:** Identificar plataforma Force10.
- **Verificación:** `show version`

## `show interfaces`

```text
show interfaces
```

- **Sirve para:** Muestra detalles de interfaces.
- **Parámetros:** Sin parámetros.
- **Caso práctico:** Consultar contadores.
- **Verificación:** `show interfaces`

## `show ip route`

```text
show ip route
```

- **Sirve para:** Consulta tabla de rutas.
- **Parámetros:** Sin parámetros.
- **Caso práctico:** Revisar siguientes saltos.
- **Verificación:** `show ip route`

## `show vlan`

```text
show vlan
```

- **Sirve para:** Muestra VLAN cuando la plataforma lo admite.
- **Parámetros:** Sin parámetros.
- **Caso práctico:** Ubicar VLAN 10.
- **Verificación:** `show vlan`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
