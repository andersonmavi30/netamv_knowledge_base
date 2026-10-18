---
tags: [cli, netdevops, operational-checks]
validation: not-lab-verified
---

# 🧭 Verificaciones operativas — ampliación · Cisco IOS

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** Classic IOS (device and feature dependent). Los comandos no se han ejecutado en equipos; confirma la sintaxis con `?` y la documentación de tu versión.

## Consulta de forwarding CEF

```text
show ip cef 198.51.100.10
```

- **Sirve para:** Revisa el resultado de forwarding en la FIB para un destino.
- **Parámetros / flags:** IP: host destino; CEF debe estar habilitado.
- **Caso real:** Comparar el forwarding instalado con la ruta esperada.
- **Filtro / comprobación:** `show ip cef 198.51.100.10`

## Vecinos EIGRP

```text
show ip eigrp neighbors
```

- **Sirve para:** Consulta vecinos EIGRP, uptime y colas.
- **Parámetros / flags:** neighbors: lista de pares; requiere EIGRP.
- **Caso real:** Buscar vecino EIGRP perdido tras un cambio.
- **Filtro / comprobación:** `show ip eigrp neighbors | include 192.0.2`

## Traducciones NAT

```text
show ip nat translations
```

- **Sirve para:** Consulta traducciones NAT inside/outside.
- **Parámetros / flags:** translations: tabla activa; requiere NAT.
- **Caso real:** Encontrar sesiones de un host interno.
- **Filtro / comprobación:** `show ip nat translations | include 192.0.2.10`

## Procesos con alto CPU

```text
show processes cpu sorted
```

- **Sirve para:** Lista procesos ordenados por CPU en IOS compatible.
- **Parámetros / flags:** sorted: ordena por consumo de CPU.
- **Caso real:** Identificar proceso detrás de alarma de CPU.
- **Filtro / comprobación:** `show processes cpu sorted | include CPU|IP Input`

## VLAN activas en trunks

```text
show interfaces trunk
```

- **Sirve para:** Muestra estado trunk, VLAN nativa y VLAN permitidas en switches.
- **Parámetros / flags:** trunk: lista trunks operativos; requiere switching.
- **Caso real:** Buscar por qué VLAN 10 no atraviesa el uplink.
- **Filtro / comprobación:** `show interfaces trunk | include 10`

> ⚠️ Comandos de diagnóstico sobre funciones opcionales no devuelven información cuando esas funciones no están configuradas. Detén los monitores interactivos al terminar.

**Referencia**: [Cisco IOS](https://www.cisco.com/c/en/us/support/ios-nx-os-software/ios-software/products-command-reference-list.html)
