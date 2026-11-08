---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Operación

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** AOS-CX 10.x; validar por modelo y release.

## `show lldp neighbor-info | include 1/1/1`

```text
show lldp neighbor-info | include 1/1/1
```

- **Sirve para:** Busca vecino LLDP de un puerto.
- **Parámetros:** include: filtra puerto.
- **Ejemplo de uso:** Identificar switch vecino.

## `show mac-address-table | include 1/1/2`

```text
show mac-address-table | include 1/1/2
```

- **Sirve para:** Busca MAC por puerto.
- **Parámetros:** include: coincidencia.
- **Ejemplo de uso:** Localizar host.

## `show ntp status`

```text
show ntp status
```

- **Sirve para:** Verifica estado NTP.
- **Parámetros:** status: consulta NTP.
- **Ejemplo de uso:** Correlacionar logs.

## `show spanning-tree | include Root`

```text
show spanning-tree | include Root
```

- **Sirve para:** Busca líneas root STP.
- **Parámetros:** include: filtra texto.
- **Ejemplo de uso:** Investigar topología.

> Validar en laboratorio. Mirror/tshark requieren soporte y autorización; deshabilita al finalizar.

## Vecinos y aprendizaje VLAN

### `show lldp neighbor-info detail`

```text
show lldp neighbor-info detail
```

- **Sirve para:** Mostrar detalles de identificación y capacidades de vecinos LLDP.
- **Parámetros:** detail: TLV detallados; requiere LLDP.
- **Ejemplo de uso:** Validar el estado sin modificar la configuración.

### `show mac-address-table vlan 10`

```text
show mac-address-table vlan 10
```

- **Sirve para:** Listar MAC aprendidas en la VLAN 10.
- **Parámetros:** vlan 10: limita la consulta a la VLAN 10.
- **Ejemplo de uso:** Validar el estado sin modificar la configuración.

> Pendiente de validación en laboratorio. AOS-CX 10.x; model/release support varies.

**Referencia:** https://arubanetworking.hpe.com/techdocs/AOS-CX/10.16/PDF/cli_6300-6400.pdf

## Verificación de multicast y spanning-tree

### `show ip igmp snooping`

```text
show ip igmp snooping
```

- **Sirve para:** Consultar el estado de IGMP snooping.
- **Parámetros:** igmp snooping: gestión de grupos multicast; requiere función disponible.
- **Ejemplo de uso:** Investigar incidencias sin cambiar configuración.

### `show spanning-tree detail`

```text
show spanning-tree detail
```

- **Sirve para:** Consultar detalle de puertos y del puente spanning-tree.
- **Parámetros:** detail: vista STP ampliada; requiere STP activo; según versión.
- **Ejemplo de uso:** Investigar incidencias sin cambiar configuración.

> Pendiente de validación en laboratorio. AOS-CX 10.x; model/release support varies.

**Referencia:** https://arubanetworking.hpe.com/techdocs/AOS-CX/10.16/PDF/cli_6300-6400.pdf
