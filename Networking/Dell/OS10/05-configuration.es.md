---
tags: [cli, dell, os10, configuration]
validation: not-lab-verified
---

# Configuración — Dell OS10

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** Dell SmartFabric OS10 (PowerSwitch hardware/release dependent). Verifica con `show version` y `?`.

## `hostname DELL-LAB`

```text
configure terminal
hostname DELL-LAB
end
```

- **Sirve para:** Configura hostname.
- **Parámetros:** hostname: nombre.
- **Caso real:** Nombrar switch.

## `copy running-configuration startup-configuration`

```text
copy running-configuration startup-configuration
```

- **Sirve para:** Guarda configuración revisada.
- **Parámetros:** running-configuration: origen; startup-configuration: destino.
- **Caso real:** Persistir cambios.

## `show startup-configuration`

```text
show startup-configuration
```

- **Sirve para:** Consulta configuración guardada.
- **Parámetros:** Sin opciones.
- **Caso real:** Comparar con running.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://www.dell.com/support/manuals/en-us/dell-emc-smartfabric-os10/smartfabric-os-user-guide-10-5-0/Filter-show-commands?guid=guid-758c857a-eba2-477a-a8f5-f0738c185e54&lang=en-us)
