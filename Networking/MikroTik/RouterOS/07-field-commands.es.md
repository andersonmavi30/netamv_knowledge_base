---
tags: [cli, field-reference]
validation: not-lab-verified
---

# 🧰 Comandos operativos — MikroTik RouterOS

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** RouterOS 7.x. Verificar comandos en equipo real.

## `/interface ethernet print detail where name="ether1"`

```text
/interface ethernet print detail where name="ether1"
```

- **Sirve para:** Consulta detalles de interfaz.
- **Parámetros:** detail: expandido; where: filtra
- **Filtro / consulta:** `/interface print where name="ether1"`

## `/ip dhcp-client print detail`

```text
/ip dhcp-client print detail
```

- **Sirve para:** Consulta clientes DHCP.
- **Parámetros:** detail: todos los detalles
- **Filtro / consulta:** `/ip dhcp-client print where interface="ether1"`

## `/ip firewall nat print stats where chain="srcnat"`

```text
/ip firewall nat print stats where chain="srcnat"
```

- **Sirve para:** Muestra contadores de NAT origen.
- **Parámetros:** stats: contadores; where: filtra
- **Filtro / consulta:** `/ip firewall nat print where action="masquerade"`

## `/ip firewall filter print where action="drop"`

```text
/ip firewall filter print where action="drop"
```

- **Sirve para:** Lista reglas drop.
- **Parámetros:** where: filtra acción
- **Filtro / consulta:** `/ip firewall filter print stats where action="drop"`

## `/ip neighbor print detail`

```text
/ip neighbor print detail
```

- **Sirve para:** Consulta vecinos descubiertos.
- **Parámetros:** detail: información ampliada
- **Filtro / consulta:** `/ip neighbor print where interface="ether2"`

## `/routing route print where dst-address="0.0.0.0/0"`

```text
/routing route print where dst-address="0.0.0.0/0"
```

- **Sirve para:** Consulta rutas por defecto.
- **Parámetros:** where: prefijo exacto
- **Filtro / consulta:** `/ip route print where dst-address="0.0.0.0/0"`

## `/interface ethernet monitor ether1 once`

```text
/interface ethernet monitor ether1 once
```

- **Sirve para:** Consulta velocidad, dúplex y propiedades operativas Ethernet de un puerto.
- **Parámetros:** ether1: puerto específico; monitor: información operativa; once: una muestra en vez de monitoreo continuo.
- **Ejemplo de uso:** Comprobar si un uplink negoció la velocidad esperada después de cambiar el cable.
- **Referencia oficial:** https://help.mikrotik.com/docs/spaces/ROS/pages/132350014/SSH

## `/interface bridge port print where bridge="bridge1"`

```text
/interface bridge port print where bridge="bridge1"
```

- **Sirve para:** Lista solo puertos miembros de bridge1, con indicadores de hardware offload.
- **Parámetros:** where: filtro por propiedad; bridge: nombre exacto del bridge.
- **Ejemplo de uso:** Comprobar si el uplink pertenece al bridge correcto y usa offload.
- **Referencia:** https://help.mikrotik.com/docs/spaces/ROS/pages/328068/Bridging+and+Switching

> Ejemplos pendientes de validación práctica. Confirma versión y sintaxis con la ayuda de CLI.
