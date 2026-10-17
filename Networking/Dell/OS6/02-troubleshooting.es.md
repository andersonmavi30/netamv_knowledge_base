---
tags: [cli, dell, os6, troubleshooting]
validation: not-lab-verified
---

# Diagnóstico — Dell OS6

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** OS6 / N-Series; CLI output filtering is available in OS6 6.6+ where supported. Verifica con `show version` y `?`.

## `ping 192.0.2.10`

```text
ping 192.0.2.10
```

- **Sirve para:** Prueba conectividad desde el switch.
- **Parámetros:** IP: destino.
- **Caso real:** Verificar alcance al gateway.

## `show interfaces counters errors gigabitethernet 1/0/1`

```text
show interfaces counters errors gigabitethernet 1/0/1
```

- **Sirve para:** Consulta errores de un puerto.
- **Parámetros:** errors: solo errores; puerto: unidad/slot/puerto.
- **Caso real:** Encontrar CRC o descartes.

## `show spanning-tree active`

```text
show spanning-tree active
```

- **Sirve para:** Consulta puertos STP activos.
- **Parámetros:** active: instancias operativas.
- **Caso real:** Investigar enlaces bloqueados.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)
