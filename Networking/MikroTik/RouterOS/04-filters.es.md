---
tags: [cli, mikrotik, routeros, filters]
vendor: MikroTik
os: "RouterOS"
versions: "7.x"
validation: not-lab-verified
---

# 🔍 Filtros operativos

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ MikroTik](../README.es.md)

**Plataforma:** MikroTik / RouterOS · **Versión orientativa:** 7.x.


## `/ip route print where dst-address="198.51.100.0/24"`

```text
/ip route print where dst-address="198.51.100.0/24"
```

- **Sirve para:** Busca un prefijo específico.
- **Parámetros/filtros:** where: filtra propiedad; =: coincidencia exacta.
- **Caso real:** Consultar ruta al laboratorio.

## `/ip firewall filter print stats where chain="forward"`

```text
/ip firewall filter print stats where chain="forward"
```

- **Sirve para:** Muestra reglas de forward y contadores.
- **Parámetros/filtros:** stats: contadores; where: limita la cadena.
- **Caso real:** Ver si el tráfico coincide con una regla.

## `/ip firewall address-list print where list="LAB-HOSTS"`

```text
/ip firewall address-list print where list="LAB-HOSTS"
```

- **Sirve para:** Lista miembros de una address-list.
- **Parámetros/filtros:** list=: nombre exacto.
- **Caso real:** Revisar hosts antes de cambios.

## `/log print where message~"login"`

```text
/log print where message~"login"
```

- **Sirve para:** Busca logs relacionados con inicios de sesión.
- **Parámetros/filtros:** message~: patrón sobre mensajes.
- **Caso real:** Revisar acceso administrativo reciente.

> Verifica los comandos y opciones mediante la ayuda CLI del equipo; ejemplos pendientes de validación en laboratorio.

**Referencias del fabricante:** [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8978498/Console) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/328084/IP+Routing) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8323088/Packet+Sniffer)
