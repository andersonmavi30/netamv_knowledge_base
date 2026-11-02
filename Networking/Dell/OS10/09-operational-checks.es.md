---
tags: [cli, networking, operational-checks]
validation: not-lab-verified
---

# Verificaciones operativas adicionales — Dell OS10

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** SmartFabric OS10, platform-specific. Confirma comando y flags con la ayuda contextual de tu versión.

## Vecinos LLDP

```text
show lldp neighbors | grep UPLINK
```

- **Sirve para:** Descubre dispositivos conectados.
- **Parámetros / flags:** neighbors: lista LLDP.
- **Caso real:** Identificar vecino uplink.
- **Filtro / verificación:** `show lldp neighbors`

## Miembros de LAG

```text
show port-channel summary | grep Po
```

- **Sirve para:** Consulta estado LAG donde aplique.
- **Parámetros / flags:** summary: resumen de miembros.
- **Caso real:** Diagnosticar enlace agregado ausente.
- **Filtro / verificación:** `show port-channel summary`

## Adyacencias OSPF

```text
show ip ospf neighbor | grep FULL
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
show ip bgp summary | grep Idle
```

- **Sirve para:** Consulta sesiones BGP en equipos compatibles.
- **Parámetros / flags:** summary: tabla de vecinos.
- **Caso real:** Buscar vecino en Active.
- **Filtro / verificación:** `show ip bgp summary | grep Active`

## `show lldp neighbors interface ethernet 1/1/1 detail`

```text
show lldp neighbors interface ethernet 1/1/1 detail
```

- **Sirve para:** Consulta los TLV LLDP anunciados por el vecino del puerto Ethernet 1/1/1.
- **Parámetros:** interface ethernet 1/1/1: selecciona interfaz local; detail: información ampliada del vecino.
- **Ejemplo de uso:** Identificar switch vecino, puerto remoto, IP de administración y capacidades al revisar cableado.
- **Referencia oficial:** https://www.dell.com/support/manuals/en-us/smartfabric-os10-emp-partner/smartfabric-os-user-guide-10-6-1-x/show-lldp-neighbors?guid=guid-cf4a7765-02fd-4278-9bcb-c49088ba61e5&lang=en-us

## `show inventory | grep -i Serial`

```text
show inventory | grep -i Serial
```

- **Sirve para:** Busca campos de número de serie en el inventario de hardware OS10.
- **Parámetros:** show inventory: chasis/módulos; | grep -i Serial: filtro sin distinguir mayúsculas.
- **Ejemplo de uso:** Identificar seriales antes de abrir un caso de soporte de hardware Dell.
- **Referencia:** https://www.dell.com/support/manuals/en-us/dell-emc-smartfabric-os10/smartfabric-os-user-guide-10-5-3/show-inventory?guid=guid-08e4f141-ddea-4d66-999b-c84edd73eff4&lang=en-us

> ⚠️ Referencia de laboratorio aún no probada; distintas plataformas Dell y Huawei pueden usar variantes de comandos.

[Referencia del fabricante](https://www.dell.com/support/home/en-us/products/networking)

## Resumen de port-channels

```text
show port-channel summary
```

- **Propósito:** Mostrar miembros y estado operativo de agregaciones de enlaces.
- **Parámetros / flags:** summary: resumen LAG; requiere port-channels configurados.
- **Uso operativo:** Comprobar enlaces agregados antes de diagnosticar LACP.
- **Referencia:** https://www.dell.com/support/home/en-us/products/networking
