---
tags: [cli, juniper, junos]
validation: not-lab-verified
---

# Consultas y estado del sistema

[English](01-show.md) · [Español](01-show.es.md) · [Índice](README.es.md)

**Compatibilidad:** Junos OS; verificar con `show version` y `?`, según EX/QFX/MX/SRX.

## `show version`

```text
show version
```

- **Sirve para:** Mostrar la versión de Junos, modelo e información de software.
- **Parámetros:** version: inventario de software; admite filtros de salida.
- **Ejemplo de uso:** Comprobar versión antes de verificar funciones.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-version.html

> Pendiente de validación en laboratorio.

## `show chassis alarms`

```text
show chassis alarms
```

- **Sirve para:** Mostrar alarmas activas del chasis y su gravedad.
- **Parámetros:** chassis: subsistema de hardware; alarms: lista de alarmas activas.
- **Ejemplo de uso:** Identificar problemas de hardware antes del mantenimiento.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-chassis-alarms.html

> Pendiente de validación en laboratorio.
