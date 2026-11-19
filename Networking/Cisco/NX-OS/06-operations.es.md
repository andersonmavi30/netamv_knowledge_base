---
tags: [cli, cisco, nx-os]
vendor: Cisco
os: NX-OS
validation: not-lab-verified
---

# Operaciones de capa 2

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ NX-OS](README.es.md)

**Plataforma:** Cisco Nexus NX-OS (Nexus 9000 / 10.x); confirmar sintaxis por modelo y versión.

## `show vlan brief`

```text
show vlan brief
```

- **Sirve para:** Listar VLAN configuradas y los puertos asociados.
- **Parámetros:** `vlan brief`: resumen de VLAN, nombres, estado y puertos; solo consulta.
- **Ejemplo de uso:** Confirmar la existencia de una VLAN al diagnosticar un puerto de acceso.
- **Referencia oficial:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Pendiente de validación en laboratorio.

## `show port-channel summary`

```text
show port-channel summary
```

- **Sirve para:** Resumir grupos port-channel, protocolo y estado de miembros.
- **Parámetros:** `port-channel summary`: enlaces agregados y estado de miembros; requiere port-channel.
- **Ejemplo de uso:** Detectar un miembro LACP que no participa en el agregado.
- **Referencia oficial:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Pendiente de validación en laboratorio.

## `show vpc brief`

```text
show vpc brief
```

- **Sirve para:** Mostrar estado del dominio vPC, peer-link y consistencia de miembros.
- **Parámetros:** `vpc brief`: estado de peer y miembros; requiere vPC configurado y compatible.
- **Ejemplo de uso:** Comprobar el peer-link vPC antes del mantenimiento de un par Nexus.
- **Referencia oficial:** https://www.cisco.com/c/en/us/support/switches/nexus-9000-series-switches/products-command-reference-list.html

> Pendiente de validación en laboratorio.
