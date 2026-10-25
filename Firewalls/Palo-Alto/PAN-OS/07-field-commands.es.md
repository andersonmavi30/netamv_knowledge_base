---
tags: [cli, palo-alto-networks, pan-os, field-commands]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Consultas adicionales de campo

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Índice PAN-OS](README.es.md)

**Plataforma:** Palo Alto Networks / PAN-OS · **Compatibilidad:** confirma la versión instalada con `show system info | match sw-version`. Los comandos pueden variar según versión, plataforma, vsys y modo de routing.

## `show arp all | match 198.51.100.1`

```text
show arp all | match 198.51.100.1
```

- **Sirve para:** Filtra ARP por IP vecina.
- **Parámetros:** match: coincide con texto.
- **Ejemplo de uso:** Validar MAC del siguiente salto WAN.

## `show high-availability path-monitoring | match failure`

```text
show high-availability path-monitoring | match failure
```

- **Sirve para:** Busca fallas del monitoreo HA.
- **Parámetros:** match: filtro; etiqueta puede variar.
- **Ejemplo de uso:** Investigar failover causado por sondas.

## `show ntp`

```text
show ntp
```

- **Sirve para:** Consulta sincronización del reloj.
- **Parámetros:** No necesita pipe: la salida es específica.
- **Ejemplo de uso:** Correlacionar hora de logs y sesiones.

## `show lldp neighbors all | match ethernet1/2`

```text
show lldp neighbors all | match ethernet1/2
```

- **Sirve para:** Filtra LLDP por puerto físico.
- **Parámetros:** match: filtro; requiere LLDP habilitado.
- **Ejemplo de uso:** Buscar switch vecino después de recableado.

## `show routing fib virtual-router default | match 203.0.113`

```text
show routing fib virtual-router default | match 203.0.113
```

- **Sirve para:** Busca prefijo sin recorrer FIB entera.
- **Parámetros:** virtual-router: instancia de rutas; match: texto de prefijo.
- **Ejemplo de uso:** Verificar siguiente salto tras ruta estática.

> Referencia breve, pendiente de validación en laboratorio. Comprueba la ayuda contextual `?`, el contexto operational (`>`) y configuration (`#`) antes de ejecutarlos.

**Referencias oficiales:** [Guía 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Guía 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
