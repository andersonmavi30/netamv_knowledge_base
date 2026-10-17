---
tags: [cli, dell, os6, packet-debug]
validation: not-lab-verified
---

# Mirroring / debug — Dell OS6

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** OS6 / N-Series; CLI output filtering is available in OS6 6.6+ where supported. Verifica con `show version` y `?`.

> ⚠️ Dell no usa un sniffer universal. Port mirroring exige un puerto de análisis y autorización. Detén las sesiones al terminar; los paquetes pueden incluir datos sensibles.

## `show monitor session 1`

```text
show monitor session 1
```

- **Sirve para:** Consulta sesión de port mirroring donde aplique.
- **Parámetros:** 1: ID de sesión; validar compatibilidad.
- **Caso real:** Enviar tráfico a Wireshark externo.

## `show statistics gigabitethernet 1/0/1`

```text
show statistics gigabitethernet 1/0/1
```

- **Sirve para:** Consulta estadísticas de paquetes.
- **Parámetros:** Puerto: unidad/slot/puerto.
- **Caso real:** Correlacionar pérdidas antes de capturar.

## `show tech-support`

```text
show tech-support
```

- **Sirve para:** Recolecta diagnóstico de soporte; puede ser sensible.
- **Parámetros:** Sin flags; salida extensa.
- **Caso real:** Investigar fallas de hardware.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)
