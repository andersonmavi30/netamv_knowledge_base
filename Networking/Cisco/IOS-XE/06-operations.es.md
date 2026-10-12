---
tags: [cli, cisco-ios-xe, operations]
validation: not-lab-verified
---

# 📋 Comandos adicionales de operación

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ Índice](README.es.md)

**Familia de versiones:** 17.x. La disponibilidad depende de modelo, licencia y versión.

## `show ip ospf neighbor`

```text
show ip ospf neighbor
```

- **Sirve para:** Consulta adyacencias OSPF.
- **Parámetros:** Sin argumentos.
- **Caso real:** Comprobar vecinos FULL.
- **Filtro/validación:** `show ip ospf neighbor | include FULL`

## `show ip bgp summary`

```text
show ip bgp summary
```

- **Sirve para:** Consulta vecinos BGP donde aplique.
- **Parámetros:** summary: salida resumida.
- **Caso real:** Buscar vecinos Idle.
- **Filtro/validación:** `show ip bgp summary | include Idle|Active`

## `show access-lists`

```text
show access-lists
```

- **Sirve para:** Muestra entradas ACL y coincidencias.
- **Parámetros:** Sin argumentos.
- **Caso real:** Buscar ACL 101.
- **Filtro/validación:** `show access-lists 101`

## `show ip arp`

```text
show ip arp
```

- **Sirve para:** Muestra vecinos ARP.
- **Parámetros:** Sin argumentos.
- **Caso real:** Revisar MAC de gateway.
- **Filtro/validación:** `show ip arp | include 192.0.2.10`

## `show interfaces status`

```text
show interfaces status
```

- **Sirve para:** Muestra puertos en plataformas switching.
- **Parámetros:** Depende del hardware.
- **Caso real:** Ubicar puertos down.
- **Filtro/validación:** `show interfaces status | include notconnect|err-disabled`

## `show logging`

```text
show logging
```

- **Sirve para:** Consulta buffer de logs.
- **Parámetros:** Sin argumentos.
- **Caso real:** Buscar flapping.
- **Filtro/validación:** `show logging | include LINK|LINEPROTO`

## `show ip route 198.51.100.10`

```text
show ip route 198.51.100.10
```

- **Sirve para:** Consulta la mejor ruta al destino.
- **Parámetros:** IP destino: búsqueda específica.
- **Caso real:** Verificar siguiente salto.
- **Filtro/validación:** `show ip route 198.51.100.10`

## `show running-config | section ^router`

```text
show running-config | section ^router
```

- **Sirve para:** Consulta bloques router.
- **Parámetros:** section: filtra bloques.
- **Caso real:** Buscar configuración OSPF o BGP.
- **Filtro/validación:** `show running-config | section ^router`

> No probado en laboratorio; verificar con la ayuda CLI y documentación de la versión antes de ejecutarlo. Los respaldos completos y las salidas de diagnóstico pueden contener datos sensibles.
