---
tags: [dell, os6, cli]
validation: not-lab-verified
---

# Consultas y estado — Dell OS6

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell Networking OS6 — generally N-series (check model/release).

## `show version`

```text
show version
```

- **Sirve para:** Muestra versión y hardware.
- **Parámetros:** Sin parámetros.
- **Caso práctico:** Identificar sistema antes de mantenimiento.
- **Verificación:** `show version`

## `show interfaces status`

```text
show interfaces status
```

- **Sirve para:** Resume puertos en modelos N compatibles.
- **Parámetros:** status: resumen de puertos.
- **Caso práctico:** Encontrar puertos desconectados.
- **Verificación:** `show interfaces status`

## `show vlan`

```text
show vlan
```

- **Sirve para:** Muestra VLAN configuradas.
- **Parámetros:** Sin parámetros.
- **Caso práctico:** Comprobar VLAN 10.
- **Verificación:** `show vlan`

## `show logging`

```text
show logging
```

- **Sirve para:** Consulta logs del sistema.
- **Parámetros:** Sin parámetros.
- **Caso práctico:** Buscar alarmas de interfaz.
- **Verificación:** `show logging`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
