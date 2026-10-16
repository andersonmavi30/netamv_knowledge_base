---
tags: [dell, os6, cli]
validation: not-lab-verified
---

# Diagnóstico de paquetes — Dell OS6

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell Networking OS6 — generally N-series (check model/release).

## `show interfaces counters`

```text
show interfaces counters
```

- **Sirve para:** Usa contadores para analizar pérdida de paquetes.
- **Parámetros:** counters: estadísticas de tráfico/errores.
- **Caso práctico:** Buscar descartes crecientes.
- **Verificación:** `show interfaces counters`

## `show logging`

```text
show logging
```

- **Sirve para:** Consulta eventos de enlaces y protocolos.
- **Parámetros:** Sin flags; filtros dependen de versión.
- **Caso práctico:** Investigar caídas frecuentes.
- **Verificación:** `show logging`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
