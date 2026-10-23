---
tags: [cli, palo-alto-networks, pan-os, filters]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# 🔍 Filtros de salida y búsquedas

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Índice PAN-OS](README.es.md)

**Compatibilidad:** PAN-OS (revisar versión exacta con `show system info | match sw-version`). Los comandos pueden variar según versión, plataforma, vsys y modo de routing.

## Usar match en lugar de grep

```text
show system info | match serial
```

- **Sirve para:** Muestra únicamente líneas con el identificador serial.
- **Parámetros y filtros:** | match: filtra texto; PAN-OS no usa el grep de Linux.
- **Caso real:** Buscar identificador de inventario.

## Excluir líneas sin interés

```text
show system info | except mac-address
```

- **Sirve para:** Oculta líneas con palabra seleccionada.
- **Parámetros y filtros:** | except: muestra líneas no coincidentes.
- **Caso real:** Consultar sistema sin campos MAC no relevantes.
- **Precaución:** No es anonimización: la salida puede conservar datos sensibles.

## Buscar gateways IKE

```text
show vpn ike-sa | match LAB-IKE
```

- **Sirve para:** Busca SA IKE del gateway por nombre.
- **Parámetros y filtros:** | match: filtro sensible a mayúsculas.
- **Caso real:** Comprobar si la VPN tiene SA IKE.
- **Precaución:** Para detalles usa comando operativo del gateway.

## Filtrar políticas NAT

```text
show running nat-policy | match LAB-NAT
```

- **Sirve para:** Localiza la regla NAT por nombre.
- **Parámetros y filtros:** | match: muestra líneas coincidentes.
- **Caso real:** Revisar regla NAT durante diagnóstico.

## Ver sesiones por aplicación

```text
show session all filter application ssl
```

- **Sirve para:** Muestra sesiones con App-ID especificada.
- **Parámetros y filtros:** filter application: filtro interno de aplicación.
- **Caso real:** Aislar sesiones SSL sin listar todas.
- **Precaución:** Solo aparecen sesiones identificadas con esa aplicación.

> Ejemplos orientativos pendientes de validación en laboratorio. Comprueba la ayuda contextual `?`, el contexto operational (`>`) y configuration (`#`) antes de ejecutarlos.

**Referencias oficiales:** [Guía 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/get-started-with-the-cli/get-help-on-command-syntax) · [Guía 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Guía 3](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
