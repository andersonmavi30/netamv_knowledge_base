---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Comandos operativos — Fortinet FortiOS

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** FortiOS 7.x. Verificar comandos en equipo real.

## `get system ha status`

```text
get system ha status | grep -i mode
```

- **Sirve para:** Consulta clúster HA.
- **Parámetros:** Sin flags
- **Filtro / consulta:** `get system ha status | grep -i mode`




## `show firewall address`

```text
show firewall address | grep -f LAB-NET
```

- **Sirve para:** Consulta objetos address.
- **Parámetros:** Sin flags
- **Filtro / consulta:** `show firewall address | grep -f LAB-NET`

## `diagnose sys sdwan member 1`

```text
diagnose sys sdwan member 1
```

- **Sirve para:** Muestra detalles del miembro SD-WAN con secuencia 1, sin listar todos los miembros.
- **Parámetros:** member 1: selecciona el ID de secuencia 1 de SD-WAN; depende de la configuración.
- **Ejemplo de uso:** Investigar el enlace WAN específico durante un incidente con el ISP.
- **Filtro / consulta:** El ID del miembro ya limita la consulta; no requiere pipe.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.7/cli-reference/235530229/diagnose-sys

> Ejemplos pendientes de validación práctica. Confirma versión y sintaxis con la ayuda de CLI.
