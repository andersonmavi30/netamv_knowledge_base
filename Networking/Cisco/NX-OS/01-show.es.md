---
tags: [cli, cisco, nx-os]
vendor: Cisco
os: NX-OS
validation: not-lab-verified
---

# Sistema y hardware

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ NX-OS](README.es.md)

**Plataforma:** Cisco Nexus NX-OS (Nexus 9000 / 10.x); confirmar sintaxis por modelo y versión.

## `show version`

```text
show version
```

- **Sirve para:** Identificar la versión NX-OS, el uptime y la plataforma Nexus.
- **Parámetros:** Sin flags: `show version` presenta información del sistema; solo lectura.
- **Ejemplo de uso:** Confirmar la versión del switch antes de diagnosticar una característica.
- **Referencia oficial:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Pendiente de validación en laboratorio.

## `show module`

```text
show module
```

- **Sirve para:** Mostrar módulos del switch Nexus y sus estados operativos.
- **Parámetros:** `module`: inventario y estado de módulos; información según modelo.
- **Ejemplo de uso:** Confirmar estado de tarjeta de línea o supervisora.
- **Referencia oficial:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Pendiente de validación en laboratorio.
