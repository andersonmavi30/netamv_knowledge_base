---
tags: [cli, juniper, junos]
validation: not-lab-verified
---

# Verificaciones operativas

[English](06-operations.md) · [Español](06-operations.es.md) · [Índice](README.es.md)

**Compatibilidad:** Junos OS; verificar modelo, versión y `?`.

## `show route summary`

```text
show route summary
```

- **Sirve para:** Resumir tamaño de tablas de enrutamiento y cantidad de rutas.
- **Parámetros:** route: información de rutas; summary: contadores por tabla.
- **Ejemplo de uso:** Identificar crecimiento inesperado de rutas.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-route.html

> Pendiente de validación en laboratorio.

## `show lldp neighbors`

```text
show lldp neighbors
```

- **Sirve para:** Listar vecinos LLDP y las interfaces locales conectadas.
- **Parámetros:** lldp neighbors: tabla de vecinos descubiertos; requiere LLDP activo.
- **Ejemplo de uso:** Identificar equipo conectado a un uplink.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-lldp-neighbors.html

> Pendiente de validación en laboratorio.

## `show ethernet-switching table`

```text
show ethernet-switching table
```

- **Sirve para:** Mostrar direcciones MAC aprendidas en capa 2.
- **Parámetros:** ethernet-switching table: tabla de MAC; solo plataformas con switching.
- **Ejemplo de uso:** Localizar una MAC y su VLAN o interfaz.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-ethernet-switching-table.html

> Pendiente de validación en laboratorio.

## `show system commit`

```text
show system commit
```

- **Sirve para:** Listar commits de configuración, autores y fechas.
- **Parámetros:** system commit: historial de confirmaciones de configuración, solo consulta.
- **Ejemplo de uso:** Relacionar una incidencia con un cambio reciente de configuración.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/operational-commands.html

> Pendiente de validación en laboratorio.
