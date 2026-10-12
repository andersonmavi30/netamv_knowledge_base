---
tags: [cli, mikrotik, routeros, interfaces]
vendor: MikroTik
os: "RouterOS"
versions: "7.x"
validation: not-lab-verified
---

# 🔌 Interfaces

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ MikroTik](../README.es.md)

**Plataforma:** MikroTik / RouterOS · **Versión orientativa:** 7.x.

## `/interface print where name="ether2"`

```text
/interface print where name="ether2"
```

- **Sirve para:** Consulta estado de una interfaz exacta.
- **Parámetros/filtros:** where name=: selecciona interfaz.
- **Caso real:** Revisar el puerto LAN.

## `/ip address add address=192.0.2.1/24 interface=ether2 comment="LAB-LAN"`

```text
/ip address add address=192.0.2.1/24 interface=ether2 comment="LAB-LAN"
```

- **Sirve para:** Asigna IPv4 a una interfaz.
- **Parámetros/filtros:** add: nueva entrada; address: IP/prefijo; interface: puerto.
- **Caso real:** Asignar IP de laboratorio a ether2.
- **Precaución:** Modifica tráfico de inmediato; usa Safe Mode al trabajar remoto.

## `/ip address print detail where interface="ether2"`

```text
/ip address print detail where interface="ether2"
```

- **Sirve para:** Verifica detalles de IP de ether2.
- **Parámetros/filtros:** detail: más datos; where: filtra interfaz.
- **Caso real:** Confirmar dirección y red.

## `/interface set [find name="ether2"] comment="LAB-LAN"`

```text
/interface set [find name="ether2"] comment="LAB-LAN"
```

- **Sirve para:** Establece comentario de interfaz.
- **Parámetros/filtros:** find: localiza por nombre; set: actualiza.
- **Caso real:** Identificar puerto LAN para diagnóstico.

> Verifica los comandos y opciones mediante la ayuda CLI del equipo; ejemplos pendientes de validación en laboratorio.

**Referencias del fabricante:** [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8978498/Console) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/328084/IP+Routing) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8323088/Packet+Sniffer)
