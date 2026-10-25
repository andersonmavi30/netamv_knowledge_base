---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Consultas y estado

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** AOS-CX 10.x; comprueba versión y sintaxis con `show version` y `?`.

## `show version | include Version`

```text
show version | include Version
```

- **Sirve para:** Identifica la versión instalada.
- **Parámetros:** include: muestra coincidencias.
- **Ejemplo de uso:** Comprobar compatibilidad antes de mantenimiento.

## `show interface brief | include 1/1/1`

```text
show interface brief | include 1/1/1
```

- **Sirve para:** Consulta estado de un puerto.
- **Parámetros:** brief: resumen; include: filtra puerto.
- **Ejemplo de uso:** Diagnosticar uplink caído.

## `show vlan | include 10`

```text
show vlan | include 10
```

- **Sirve para:** Busca una VLAN por texto.
- **Parámetros:** include: coincidencia textual.
- **Ejemplo de uso:** Verificar VLAN 10.

## `show ip route | include 198.51.100`

```text
show ip route | include 198.51.100
```

- **Sirve para:** Busca rutas con prefijo.
- **Parámetros:** include: líneas; requiere L3.
- **Ejemplo de uso:** Revisar red remota.

> Ejemplos pendientes de validación en laboratorio; comandos y filtros pueden variar según versión y equipo.
