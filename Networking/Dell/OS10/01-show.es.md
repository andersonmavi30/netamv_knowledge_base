---
tags: [cli, dell, os10, show]
validation: not-lab-verified
---

# Consultas y estado — Dell OS10

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** Dell SmartFabric OS10 (PowerSwitch hardware/release dependent). Verifica con `show version` y `?`.

## `show version`

```text
show version | grep Version
```

- **Sirve para:** Identifica versión OS10.
- **Parámetros:** Sin opciones.
- **Caso real:** Comprobar versión.

## `show interface status`

```text
show interface status | grep down
```

- **Sirve para:** Resume puertos Ethernet.
- **Parámetros:** status: resumen.
- **Caso real:** Buscar puertos caídos.

## `show ip route`

```text
show ip route | grep 198.51.100
```

- **Sirve para:** Muestra tabla de rutas.
- **Parámetros:** Sin opciones.
- **Caso real:** Buscar prefijo.

## `show vlan`

```text
show vlan | grep 10
```

- **Sirve para:** Muestra VLAN.
- **Parámetros:** Sin opciones.
- **Caso real:** Revisar VLAN 10.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://www.dell.com/support/manuals/en-us/dell-emc-smartfabric-os10/smartfabric-os-user-guide-10-5-0/Filter-show-commands?guid=guid-758c857a-eba2-477a-a8f5-f0738c185e54&lang=en-us)
