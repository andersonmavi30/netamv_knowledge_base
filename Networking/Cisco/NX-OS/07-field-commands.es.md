---
tags: [cli, cisco, nx-os]
vendor: Cisco
os: NX-OS
validation: not-lab-verified
---

# Protocolos de enrutamiento

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ NX-OS](README.es.md)

**Plataforma:** Cisco Nexus NX-OS (Nexus 9000 / 10.x); confirmar sintaxis por modelo y versión.

## `show ip route summary`

```text
show ip route summary
```

- **Sirve para:** Mostrar resumen de rutas IPv4 instaladas y sus protocolos de origen.
- **Parámetros:** `ip route summary`: tabla IPv4 resumida; el contexto de VRF puede alterar la salida.
- **Ejemplo de uso:** Comparar cantidad de rutas antes y después de un cambio autorizado.
- **Referencia oficial:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Pendiente de validación en laboratorio; confirma disponibilidad de opciones en tu versión.
