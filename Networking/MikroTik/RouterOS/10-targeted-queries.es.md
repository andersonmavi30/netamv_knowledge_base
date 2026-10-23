---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Búsquedas de operación — MikroTik RouterOS

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Índice](README.es.md)

> Los ejemplos son orientativos: valida el modelo, release y ayuda de CLI antes de usarlos.

## Contadores de firewall raw

```text
/ip firewall raw print stats where chain="prerouting"
```

- **Sirve para:** Contadores de firewall raw.
- **Opciones y filtros:** stats: paquetes y bytes; where: cadena
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Vecinos OSPF Full

```text
/routing ospf neighbor print where state="Full"
```

- **Sirve para:** Vecinos OSPF Full.
- **Opciones y filtros:** where: estado exacto
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Membresía VLAN bridge

```text
/interface bridge vlan print where vlan-ids=10
```

- **Sirve para:** Membresía VLAN bridge.
- **Opciones y filtros:** vlan-ids: VLAN configurada
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Búsqueda en caché DNS

```text
/ip dns cache print where name~"example"
```

- **Sirve para:** Búsqueda en caché DNS.
- **Opciones y filtros:** ~: patrón en name
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Sincronización cliente NTP

```text
/system ntp client print
```

- **Sirve para:** Sincronización cliente NTP.
- **Opciones y filtros:** print: estado cliente
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

