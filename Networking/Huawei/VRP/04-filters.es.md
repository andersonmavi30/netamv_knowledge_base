---
tags: [cli, huawei, vrp, filters]
vendor: Huawei
os: "VRP"
versions: "VRP (generic; confirm your device's release)"
validation: not-lab-verified
---

# 🔍 Filtros operativos

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Huawei](../README.es.md)

**Plataforma:** Huawei / VRP · **Versión orientativa:** VRP (generic; confirm your device's release).

## `display current-configuration | include sysname`

```text
display current-configuration | include sysname
```

- **Sirve para:** Busca hostname configurado.
- **Parámetros/filtros:** | include: conserva coincidencias.
- **Caso real:** Identificar equipo sin leer toda la config.


## `display logbuffer | include ERROR`

```text
display logbuffer | include ERROR
```

- **Sirve para:** Busca mensajes ERROR.
- **Parámetros/filtros:** El filtrado puede variar entre versiones.
- **Caso real:** Reducir ruido de logs.

## `display current-configuration | begin interface`

```text
display current-configuration | begin interface
```

- **Sirve para:** Muestra salida desde la primera línea de interfaz.
- **Parámetros/filtros:** begin: muestra coincidencia y todo lo posterior.
- **Caso real:** Saltar configuración global.

## `display current-configuration | exclude description`

```text
display current-configuration | exclude description
```

- **Sirve para:** Oculta líneas description (no bloques completos).
- **Parámetros/filtros:** exclude: elimina coincidencias.
- **Caso real:** Revisar otros ajustes de configuración.

> Verifica los comandos y opciones mediante la ayuda CLI del equipo; ejemplos pendientes de validación en laboratorio.

**Referencias del fabricante:** [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100333403/cdd85713/basic-interface-configuration-commands) · [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100335692/c1ebaf03/basic-ip-routing-configuration)
