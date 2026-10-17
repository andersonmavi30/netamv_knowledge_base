---
tags: [cli, dell, os6, configuration]
validation: not-lab-verified
---

# Configuración — Dell OS6

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** OS6 / N-Series; CLI output filtering is available in OS6 6.6+ where supported. Verifica con `show version` y `?`.

## `hostname DELL-LAB`

```text
configure
hostname DELL-LAB
exit
```

- **Sirve para:** Cambia hostname.
- **Parámetros:** hostname: nombre.
- **Caso real:** Nombrar switch de prueba.

## `vlan 10`

```text
configure
vlan 10
exit
exit
```

- **Sirve para:** Crea VLAN 10 en equipos OS6 compatibles.
- **Parámetros:** vlan 10: ID de VLAN.
- **Caso real:** Preparar LAN de prueba.

## `copy running-config startup-config`

```text
copy running-config startup-config
```

- **Sirve para:** Guarda configuración activa.
- **Parámetros:** running-config: origen; startup-config: destino.
- **Caso real:** Guardar cambios aprobados.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)
