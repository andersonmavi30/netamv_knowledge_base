---
tags: [cli, palo-alto-networks, pan-os, interfaces]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Interfaces y enrutamiento

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Índice PAN-OS](README.es.md)

**Plataforma:** Palo Alto Networks / PAN-OS · **Compatibilidad:** confirma la versión instalada con `show system info | match sw-version`. Los comandos pueden variar según versión, plataforma, vsys y modo de routing.

## `show arp all | match 192.0.2.10`

```text
show arp all | match 192.0.2.10
```

- **Sirve para:** Busca un vecino específico en la tabla ARP.
- **Parámetros:** all: entradas ARP; match: coincidencia.
- **Ejemplo de uso:** Comprobar si se aprendió la MAC del siguiente salto.

## `show routing fib virtual-router default | match 198.51.100`

```text
show routing fib virtual-router default | match 198.51.100
```

- **Sirve para:** Busca un prefijo en la tabla de forwarding.
- **Parámetros:** virtual-router default: nombre de VR ejemplo; match: texto del prefijo.
- **Ejemplo de uso:** Revisar ruta seleccionada hacia red remota.
- **Precaución:** Con Advanced Routing / logical router puede variar; valida en el equipo.

## `show interface ethernet1/2`

```text
show interface ethernet1/2
```

- **Sirve para:** Consulta enlace y contadores de una interfaz.
- **Parámetros:** ethernet1/2: puerto de dataplane.
- **Ejemplo de uso:** Revisar uplink SFP intermitente.

## `show lldp neighbors all | match ethernet1/1`

```text
show lldp neighbors all | match ethernet1/1
```

- **Sirve para:** Busca vecinos LLDP de un puerto en equipos compatibles.
- **Parámetros:** all: todos los vecinos; match: interfaz elegida.
- **Ejemplo de uso:** Identificar switch conectado antes de mover cable.
- **Precaución:** Requiere LLDP habilitado/disponible.

## `show counter interface ethernet1/1`

```text
show counter interface ethernet1/1
```

- **Sirve para:** Consulta contadores de un puerto.
- **Parámetros:** interface: selecciona puerto, sin pipe adicional.
- **Ejemplo de uso:** Investigar errores físicos o descartes WAN.

> Referencia breve, pendiente de validación en laboratorio. Comprueba la ayuda contextual `?`, el contexto operational (`>`) y configuration (`#`) antes de ejecutarlos.

**Referencias oficiales:** [Guía 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Guía 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
