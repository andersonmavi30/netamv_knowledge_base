---
tags: [cli, juniper, junos]
validation: not-lab-verified
---

# Comprobaciones de protocolos de enrutamiento

[English](07-field-commands.md) · [Español](07-field-commands.es.md) · [Índice](README.es.md)

**Compatibilidad:** Junos OS; verificar modelo, versión y `?`.

## `show ospf neighbor`

```text
show ospf neighbor
```

- **Sirve para:** Mostrar vecinos OSPF y sus estados de adyacencia.
- **Parámetros:** ospf neighbor: estados de vecinos; requiere OSPF configurado.
- **Ejemplo de uso:** Identificar vecinos que no alcanzan el estado Full.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-ospf-neighbor.html

> Pendiente de validación en laboratorio.

## `show bgp summary`

```text
show bgp summary
```

- **Sirve para:** Mostrar estados de vecinos BGP y resumen de prefijos recibidos.
- **Parámetros:** bgp summary: tabla resumida de vecinos; requiere BGP.
- **Ejemplo de uso:** Detectar sesiones Idle o Active antes de revisar políticas.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-bgp-summary.html

> Pendiente de validación en laboratorio.
