---
tags: [cli, networking, operational-checks]
validation: not-lab-verified
---

# Verificaciones operativas adicionales — Dell OS9

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** OS9 / Force10, platform-specific. Confirma comando y flags con la ayuda contextual de tu versión.

## Vecinos LLDP

```text
show lldp neighbors | grep UPLINK
```

- **Sirve para:** Descubre dispositivos vecinos.
- **Parámetros / flags:** neighbors: vecinos LLDP.
- **Caso real:** Validar enlace físico.
- **Filtro / verificación:** `show lldp neighbors`

## Resumen de LAG

```text
show port-channel summary | grep Po
```

- **Sirve para:** Revisa estado de agregación donde aplique.
- **Parámetros / flags:** summary: resumen de miembros.
- **Caso real:** Buscar miembro suspendido.
- **Filtro / verificación:** `show port-channel summary`

## Resumen BGP

```text
show ip bgp summary | grep Idle
```

- **Sirve para:** Consulta sesiones BGP en equipos L3.
- **Parámetros / flags:** summary: vecinos resumidos.
- **Caso real:** Localizar vecino Idle.
- **Filtro / verificación:** `show ip bgp summary | grep Idle`

## Aprendizaje MAC

```text
show mac-address-table | grep 0011
```

- **Sirve para:** Muestra MAC L2 aprendidas en equipos compatibles.
- **Parámetros / flags:** Sin parámetros; sintaxis puede variar.
- **Caso real:** Identificar MAC en trunk.
- **Filtro / verificación:** `show mac-address-table`

## Vecinos OSPF

```text
show ip ospf neighbor | grep FULL
```

- **Sirve para:** Muestra adyacencias OSPF.
- **Parámetros / flags:** Sin parámetros; requiere OSPF.
- **Caso real:** Comprobar vecinos.
- **Filtro / verificación:** `show ip ospf neighbor`

## `show processes cpu summary`

```text
show processes cpu summary
```

- **Sirve para:** Muestra un resumen del consumo de CPU de procesos del plano de control en OS9 compatible.
- **Parámetros:** processes cpu: monitoreo de CPU; summary: estadísticas resumidas (según plataforma).
- **Ejemplo de uso:** Comprobar consumo del plano de control antes de habilitar debugging intensivo.
- **Referencia oficial:** https://www.dell.com/support/manuals/en-us/dell-emc-os-9/s6010-on-9.14.2.4-cli/show-processes-cpu?guid=guid-9e687ea4-6b17-485c-aded-809d15df998f&lang=en-us

## `show ip bgp neighbors 192.0.2.1 | grep "BGP state"`

```text
show ip bgp neighbors 192.0.2.1 | grep "BGP state"
```

- **Sirve para:** Consulta el estado de la máquina BGP de un vecino específico.
- **Parámetros:** 192.0.2.1: IP de vecino; | grep: muestra su campo de estado BGP.
- **Ejemplo de uso:** Investigar por qué un peer BGP no alcanza Established.
- **Referencia:** https://www.dell.com/support/manuals/en-za/dell-emc-smartfabric-os10/techsheet-os10-5-3-0-os9-pub/border-gateway-protocol?guid=guid-8520ae6f-95e0-411e-986f-978c419f8d0f&lang=en-us

> ⚠️ Referencia de laboratorio aún no probada; distintas plataformas Dell y Huawei pueden usar variantes de comandos.

[Referencia del fabricante](https://www.dell.com/support/home/en-us/products/networking)

## Registro de eventos del sistema

```text
show logging
```

- **Propósito:** Mostrar mensajes de eventos almacenados en Force10 OS9.
- **Parámetros / flags:** logging: buffer local; volumen y severidad según configuración.
- **Uso operativo:** Relacionar flaps de enlace y reinicios de vecinos de routing.
- **Referencia:** https://www.dell.com/support/home/en-us/products/networking

## Contadores de interfaces

```text
show interfaces counters
```

- **Propósito:** Consultar contadores y errores de interfaces.
- **Parámetros / flags:** counters: estadísticas de paquetes; depende del modelo.
- **Uso operativo:** Buscar incrementos anormales durante un incidente.

## Estado operativo de puertos

```text
show interfaces status
```

- **Propósito:** Resumir estado de enlace y de operación en switches OS9 compatibles.
- **Parámetros / flags:** status: resumen de estado; disponibilidad según plataforma.
- **Uso operativo:** Encontrar enlaces caídos antes de revisar transceptores.
- **Validación:** Pendiente de prueba en laboratorio; verificar versión y permisos.

## Resumen de software y hardware OS9

```text
show version
```

- **Propósito:** Consultar versión Force10 OS9 e información de la plataforma.
- **Parámetros / flags:** version: versión y datos de hardware; varía según modelo.
- **Uso operativo:** Registrar versión antes de diagnósticos específicos.
- **Validación:** Pendiente de laboratorio; confirmar versión y contexto CLI.
