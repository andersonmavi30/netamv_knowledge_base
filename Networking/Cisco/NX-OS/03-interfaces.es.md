---
tags: [cli, cisco, nx-os]
vendor: Cisco
os: NX-OS
validation: not-lab-verified
---

# Interfaces y contadores

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ NX-OS](README.es.md)

**Plataforma:** Cisco Nexus NX-OS (Nexus 9000 / 10.x); confirmar sintaxis por modelo y versión.

## `show interface status`

```text
show interface status
```

- **Sirve para:** Resumir estado de interfaces, VLAN asignada, dúplex, velocidad y medio.
- **Parámetros:** `interface status`: resumen de puertos sin modificar interfaces.
- **Ejemplo de uso:** Detectar uplinks caídos o puertos con velocidad inesperada.
- **Referencia oficial:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Pendiente de validación en laboratorio.

## `show interface ethernet1/1`

```text
show interface ethernet1/1
```

- **Sirve para:** Consultar estado operativo y contadores detallados de Ethernet1/1.
- **Parámetros:** `ethernet1/1`: interfaz Ethernet Nexus de ejemplo; sustituye por puerto real.
- **Ejemplo de uso:** Revisar pérdidas o errores en el enlace hacia un servidor.
- **Referencia oficial:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Pendiente de validación en laboratorio.
