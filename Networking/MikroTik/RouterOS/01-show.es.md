---
tags: [cli, mikrotik, routeros, show]
vendor: MikroTik
os: "RouterOS"
versions: "7.x"
validation: not-lab-verified
---

# 🔎 Consultas y estado

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ MikroTik](../README.es.md)

**Plataforma:** MikroTik / RouterOS · **Versión orientativa:** 7.x.

## `/system resource print`

```text
/system resource print
```

- **Sirve para:** Recursos del equipo y versión.
- **Parámetros/filtros:** print: muestra propiedades.
- **Caso real:** Ver CPU y versión de RouterOS.

## `/system identity print`

```text
/system identity print
```

- **Sirve para:** Muestra nombre del router.
- **Parámetros/filtros:** identity: menú del hostname.
- **Caso real:** Identificar el equipo antes de cambios.

## `/interface print where name~"ether"`

```text
/interface print where name~"ether"
```

- **Sirve para:** Lista solo interfaces Ethernet.
- **Parámetros/filtros:** where: filtra; ~: busca patrón en name.
- **Caso real:** Encontrar ether1/ether2.

## `/ip address print where interface="ether2"`

```text
/ip address print where interface="ether2"
```

- **Sirve para:** Busca direcciones en ether2.
- **Parámetros/filtros:** where: igualdad exacta de propiedad.
- **Caso real:** Confirmar IP de la LAN.

## `/ip route print where dst-address="0.0.0.0/0"`

```text
/ip route print where dst-address="0.0.0.0/0"
```

- **Sirve para:** Muestra rutas predeterminadas.
- **Parámetros/filtros:** dst-address: prefijo exacto.
- **Caso real:** Revisar gateway de Internet.

> Verifica los comandos y opciones mediante la ayuda CLI del equipo; ejemplos pendientes de validación en laboratorio.

**Referencias del fabricante:** [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8978498/Console) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/328084/IP+Routing) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8323088/Packet+Sniffer)
