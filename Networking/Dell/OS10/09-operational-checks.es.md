---
tags: [cli, networking, operational-checks]
validation: not-lab-verified
---

# Verificaciones operativas adicionales — Dell OS10

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** SmartFabric OS10, platform-specific. Confirma comando y flags con la ayuda contextual de tu versión.

## Vecinos LLDP

```text
show lldp neighbors
```

- **Sirve para:** Descubre dispositivos conectados.
- **Parámetros / flags:** neighbors: lista LLDP.
- **Caso real:** Identificar vecino uplink.
- **Filtro / verificación:** `show lldp neighbors`

## Miembros de LAG

```text
show port-channel summary
```

- **Sirve para:** Consulta estado LAG donde aplique.
- **Parámetros / flags:** summary: resumen de miembros.
- **Caso real:** Diagnosticar enlace agregado ausente.
- **Filtro / verificación:** `show port-channel summary`

## Adyacencias OSPF

```text
show ip ospf neighbor
```

- **Sirve para:** Consulta estado de vecinos OSPF.
- **Parámetros / flags:** Sin flags; requiere configuración routing.
- **Caso real:** Buscar vecino no Full.
- **Filtro / verificación:** `show ip ospf neighbor`

## Diagnóstico de transceptor

```text
show interface ethernet 1/1/1 transceiver
```

- **Sirve para:** Consulta módulo óptico en plataforma compatible.
- **Parámetros / flags:** ethernet: interfaz física; transceiver: óptica.
- **Caso real:** Revisar óptico defectuoso.
- **Filtro / verificación:** `show interface ethernet 1/1/1 transceiver`

## Resumen BGP

```text
show ip bgp summary
```

- **Sirve para:** Consulta sesiones BGP en equipos compatibles.
- **Parámetros / flags:** summary: tabla de vecinos.
- **Caso real:** Buscar vecino en Active.
- **Filtro / verificación:** `show ip bgp summary | grep Active`

> ⚠️ Referencia de laboratorio aún no probada; distintas plataformas Dell y Huawei pueden usar variantes de comandos.

[Referencia del fabricante](https://www.dell.com/support/home/en-us/products/networking)
