---
tags: [cli, mikrotik, routeros, configuration]
vendor: MikroTik
os: "RouterOS"
versions: "7.x"
validation: not-lab-verified
---

# ⚙️ Configuración general

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ MikroTik](../README.es.md)

**Plataforma:** MikroTik / RouterOS · **Versión orientativa:** 7.x.

## `/system identity set name=MT-LAB`

```text
/system identity set name=MT-LAB
```

- **Sirve para:** Cambia hostname.
- **Parámetros/filtros:** set name=: asigna nombre.
- **Caso real:** Nombrar un router de laboratorio.

## `/ip route add dst-address=198.51.100.0/24 gateway=192.0.2.254 comment="LAB"`

```text
/ip route add dst-address=198.51.100.0/24 gateway=192.0.2.254 comment="LAB"
```

- **Sirve para:** Agrega ruta estática.
- **Parámetros/filtros:** dst-address: prefijo; gateway: siguiente salto.
- **Caso real:** Enrutar tráfico a una red de laboratorio.
- **Precaución:** Verifica siguiente salto y reglas de routing antes de aplicar.

## `/ip firewall address-list add list=LAB-HOSTS address=192.0.2.10 comment="LAB"`

```text
/ip firewall address-list add list=LAB-HOSTS address=192.0.2.10 comment="LAB"
```

- **Sirve para:** Agrega un host a una address-list.
- **Parámetros/filtros:** list: grupo; address: IP miembro; comment: etiqueta.
- **Caso real:** Agrupar destinos del laboratorio.


> Verifica los comandos y opciones mediante la ayuda CLI del equipo; ejemplos pendientes de validación en laboratorio.

**Referencias del fabricante:** [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8978498/Console) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/328084/IP+Routing) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8323088/Packet+Sniffer)
