---
tags: [cli, dell, os6, show]
validation: not-lab-verified
---

# Consultas y estado — Dell OS6

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** OS6 / N-Series; CLI output filtering is available in OS6 6.6+ where supported. Verifica con `show version` y `?`.

## `show version`

```text
show version | include Version
```

- **Sirve para:** Identifica sistema y hardware.
- **Parámetros:** Sin opciones.
- **Caso real:** Confirmar OS6.

## `show interfaces status`

```text
show interfaces status | include 1/0/1
```

- **Sirve para:** Muestra estados de puertos.
- **Parámetros:** status: vista resumida.
- **Caso real:** Localizar enlaces inactivos.

## `show vlan`

```text
show vlan | include 10
```

- **Sirve para:** Lista VLAN configuradas.
- **Parámetros:** Sin opciones.
- **Caso real:** Buscar VLAN 10.

## `show ip route`

```text
show ip route | include 198.51.100
```

- **Sirve para:** Muestra rutas IPv4.
- **Parámetros:** Sin opciones; requiere L3.
- **Caso real:** Verificar ruta predeterminada.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)
