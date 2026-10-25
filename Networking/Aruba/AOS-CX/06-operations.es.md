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
