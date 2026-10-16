---
tags: [dell, os6, cli]
validation: not-lab-verified
---

# Diagnóstico — Dell OS6

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell Networking OS6 — generally N-series (check model/release).

## `ping 192.0.2.10`

```text
ping 192.0.2.10
```

- **Sirve para:** Prueba conectividad IPv4.
- **Parámetros:** IP: destino.
- **Caso práctico:** Probar gestión.
- **Verificación:** `ping 192.0.2.10`

## `show interfaces counters`

```text
show interfaces counters
```

- **Sirve para:** Consulta contadores en modelos compatibles.
- **Parámetros:** counters: estadísticas de interfaces.
- **Caso práctico:** Buscar errores o descartes.
- **Verificación:** `show interfaces counters`

## `show logging`

```text
show logging
```

- **Sirve para:** Revisa errores y eventos.
- **Parámetros:** Sin parámetros.
- **Caso práctico:** Identificar hora de caída.
- **Verificación:** `show logging`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
