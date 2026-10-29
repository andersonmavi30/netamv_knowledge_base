---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Consultas de interfaces

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** AOS-CX 10.x; comprueba versión y sintaxis con `show version` y `?`.

## `show interface 1/1/3`

```text
show interface 1/1/3
```

- **Sirve para:** Consulta contadores del puerto.
- **Parámetros:** 1/1/3: interfaz.
- **Ejemplo de uso:** Diagnosticar errores.

## `show ip interface brief | include vlan10`

```text
show ip interface brief | include vlan10
```

- **Sirve para:** Busca dirección SVI.
- **Parámetros:** include: texto interfaz VLAN.
- **Ejemplo de uso:** Ver gateway de gestión.

## `show running-config | begin interface 1/1/3`

```text
show running-config | begin interface 1/1/3
```

- **Sirve para:** Consulta configuración desde puerto.
- **Parámetros:** begin: desde primera coincidencia.
- **Ejemplo de uso:** Revisar configuración.

## `show interface brief | include down`

```text
show interface brief | include down
```

- **Sirve para:** Busca puertos caídos.
- **Parámetros:** include: líneas coincidentes.
- **Ejemplo de uso:** Encontrar enlaces inactivos.

## `show interface brief | include UPLINK`

```text
show interface brief | include UPLINK
```

**Alternativa para un puerto:**

```text
show interface 1/1/1 | include Description
```

- **Sirve para:** Busca puertos con UPLINK en la columna Description; revisa un puerto si el resumen omite etiquetas.
- **Parámetros:** brief: estado resumido (y descripciones si son compatibles); | include: líneas coincidentes.
- **Ejemplo de uso:** Encontrar el uplink y comprobar su descripción y estado.
- **Compatibilidad:** AOS-CX; que `brief` muestre descripciones depende de versión/plataforma.
- **Referencia:** [Documentación del fabricante](https://arubanetworking.hpe.com/techdocs/AOS-CX/10.16/HTML/fundamentals_8100-83xx-93xx-100xx/Content/Chp_IfaceCfg/Iface_cmds/sho-int-10.htm)

> Ejemplos pendientes de validación en laboratorio; comandos y filtros pueden variar según versión y equipo.
