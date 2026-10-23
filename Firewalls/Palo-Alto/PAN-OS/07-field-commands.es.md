---
tags: [cli, palo-alto-networks, pan-os, field-commands]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# 🧰 Consultas adicionales de campo

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Índice PAN-OS](README.es.md)

**Compatibilidad:** PAN-OS (revisar versión exacta con `show system info | match sw-version`). Los comandos pueden variar según versión, plataforma, vsys y modo de routing.

## Buscar ARP por IP

```text
show arp all | match 198.51.100.1
```

- **Sirve para:** Filtra ARP por IP vecina.
- **Parámetros y filtros:** match: coincide con texto.
- **Caso real:** Validar MAC del siguiente salto WAN.

## Buscar fallas monitoreo HA

```text
show high-availability path-monitoring | match failure
```

- **Sirve para:** Busca fallas del monitoreo HA.
- **Parámetros y filtros:** match: filtro; etiqueta puede variar.
- **Caso real:** Investigar failover causado por sondas.

## Comprobar NTP

```text
show ntp
```

- **Sirve para:** Consulta sincronización del reloj.
- **Parámetros y filtros:** No necesita pipe: la salida es específica.
- **Caso real:** Correlacionar hora de logs y sesiones.

## Consultar vecinos de puerto

```text
show lldp neighbors all | match ethernet1/2
```

- **Sirve para:** Filtra LLDP por puerto físico.
- **Parámetros y filtros:** match: filtro; requiere LLDP habilitado.
- **Caso real:** Buscar switch vecino después de recableado.

## Revisar ruta específica en FIB

```text
show routing fib virtual-router default | match 203.0.113
```

- **Sirve para:** Busca prefijo sin recorrer FIB entera.
- **Parámetros y filtros:** virtual-router: instancia de rutas; match: texto de prefijo.
- **Caso real:** Verificar siguiente salto tras ruta estática.

> Ejemplos orientativos pendientes de validación en laboratorio. Comprueba la ayuda contextual `?`, el contexto operational (`>`) y configuration (`#`) antes de ejecutarlos.

**Referencias oficiales:** [Guía 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Guía 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
