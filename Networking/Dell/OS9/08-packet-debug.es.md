---
tags: [dell, os9, cli]
validation: not-lab-verified
---

# Diagnóstico de paquetes — Dell OS9

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell Networking OS9 / FTOS — Force10-derived platforms, model-dependent.

## `show interfaces`

```text
show interfaces
```

- **Sirve para:** Usa contadores para identificar fallos.
- **Parámetros:** Consulta contadores del puerto.
- **Caso práctico:** Revisar errores y descartes.
- **Verificación:** `show interfaces`

## `show logging`

```text
show logging
```

- **Sirve para:** Revisa eventos; no es captura PCAP.
- **Parámetros:** Sin flags.
- **Caso práctico:** Analizar flapping.
- **Verificación:** `show logging`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
