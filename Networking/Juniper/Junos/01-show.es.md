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

## `show system uptime`

```text
show system uptime
```

- **Sirve para:** Mostrar hora actual, tiempo desde arranque e inicio de protocolos cuando esté disponible.
- **Parámetros:** system uptime: reloj y tiempo activo; campos según versión.
- **Ejemplo de uso:** Relacionar un incidente con el último reinicio.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/operational-commands.html

> Pendiente de validación en laboratorio.

## `show chassis hardware extensive`

```text
show chassis hardware extensive
```

- **Sirve para:** Mostrar detalles de chasis, componentes FRU e identificación de hardware.
- **Parámetros:** chassis hardware: inventario; extensive: información ampliada.
- **Ejemplo de uso:** Consultar componentes antes de reemplazar hardware.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/operational-commands.html

> Pendiente de validación en laboratorio.

## `show chassis routing-engine`

```text
show chassis routing-engine
```

- **Sirve para:** Mostrar estado del Routing Engine, memoria y utilización CPU.
- **Parámetros:** chassis routing-engine: métricas de RE; varían por plataforma.
- **Ejemplo de uso:** Revisar carga del plano de control ante lentitud de protocolos.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/operational-commands.html

> Pendiente de validación en laboratorio.
