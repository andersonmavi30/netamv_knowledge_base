---
tags: [cli, palo-alto-networks, pan-os, interfaces]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# 🔌 Interfaces y enrutamiento

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Índice PAN-OS](README.es.md)

**Compatibilidad:** PAN-OS (revisar versión exacta con `show system info | match sw-version`). Los comandos pueden variar según versión, plataforma, vsys y modo de routing.

## Buscar ARP de host

```text
show arp all | match 192.0.2.10
```

- **Sirve para:** Busca un vecino específico en la tabla ARP.
- **Parámetros y filtros:** all: entradas ARP; match: coincidencia.
- **Caso real:** Comprobar si se aprendió la MAC del siguiente salto.

## Consultar prefijo en la FIB

```text
show routing fib virtual-router default | match 198.51.100
```

- **Sirve para:** Busca un prefijo en la tabla de forwarding.
- **Parámetros y filtros:** virtual-router default: nombre de VR ejemplo; match: texto del prefijo.
- **Caso real:** Revisar ruta seleccionada hacia red remota.
- **Precaución:** Con Advanced Routing / logical router puede variar; valida en el equipo.

## Revisar estado de interfaz óptica

```text
show interface ethernet1/2
```

- **Sirve para:** Consulta enlace y contadores de una interfaz.
- **Parámetros y filtros:** ethernet1/2: puerto de dataplane.
- **Caso real:** Revisar uplink SFP intermitente.

## Revisar vecinos LLDP

```text
show lldp neighbors all | match ethernet1/1
```

- **Sirve para:** Busca vecinos LLDP de un puerto en equipos compatibles.
- **Parámetros y filtros:** all: todos los vecinos; match: interfaz elegida.
- **Caso real:** Identificar switch conectado antes de mover cable.
- **Precaución:** Requiere LLDP habilitado/disponible.

## Revisar contadores de interfaz

```text
show counter interface ethernet1/1
```

- **Sirve para:** Consulta contadores de un puerto.
- **Parámetros y filtros:** interface: selecciona puerto, sin pipe adicional.
- **Caso real:** Investigar errores físicos o descartes WAN.

> Ejemplos orientativos pendientes de validación en laboratorio. Comprueba la ayuda contextual `?`, el contexto operational (`>`) y configuration (`#`) antes de ejecutarlos.

**Referencias oficiales:** [Guía 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Guía 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
