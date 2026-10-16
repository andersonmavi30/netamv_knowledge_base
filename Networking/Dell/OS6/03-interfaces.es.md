---
tags: [dell, os6, cli]
validation: not-lab-verified
---

# Interfaces — Dell OS6

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell Networking OS6 — generally N-series (check model/release).

## `show interfaces status`

```text
show interfaces status
```

- **Sirve para:** Revisa puertos antes de cambiar.
- **Parámetros:** status: resumen.
- **Caso práctico:** Revisar estado uplink.
- **Verificación:** `show interfaces status`

## `configure`

```text
configure
interface gigabitethernet 1/0/1
 description LAB-UPLINK
exit
exit
```

- **Sirve para:** Etiqueta puerto de prueba; sintaxis varía según modelo.
- **Parámetros:** interface: selecciona puerto; description: etiqueta.
- **Caso práctico:** Identificar uplink de laboratorio.
- **Verificación:** `show interfaces status`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
