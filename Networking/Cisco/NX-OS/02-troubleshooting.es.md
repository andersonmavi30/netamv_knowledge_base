---
tags: [cli, cisco, nx-os]
vendor: Cisco
os: NX-OS
validation: not-lab-verified
---

# Logs y diagnóstico

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ NX-OS](README.es.md)

**Plataforma:** Cisco Nexus NX-OS (Nexus 9000 / 10.x); confirmar sintaxis por modelo y versión.

## `show logging last 50`

```text
show logging last 50
```

- **Sirve para:** Mostrar los últimos 50 mensajes syslog del buffer cuando la versión NX-OS admite esta opción.
- **Parámetros:** `logging`: consulta mensajes del sistema; `last 50`: limita a los últimos 50 registros.
- **Ejemplo de uso:** Relacionar un flap de interfaz o evento vPC con registros del sistema.
- **Referencia oficial:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Pendiente de validación en laboratorio; confirma disponibilidad de opciones en tu versión.
