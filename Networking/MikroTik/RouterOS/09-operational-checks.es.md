---
tags: [cli, netdevops, operational-checks]
validation: not-lab-verified
---

# 🧭 Verificaciones operativas — ampliación · MikroTik RouterOS

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** RouterOS 7.x (model and installed features vary). Los comandos no se han ejecutado en equipos; confirma la sintaxis con `?` y la documentación de tu versión.

## MAC aprendidas por puerto bridge

```text
/interface bridge host print where on-interface="ether2"
```

- **Sirve para:** Encuentra MAC aprendidas detrás de un puerto físico.
- **Parámetros / flags:** where: filtra propiedades; on-interface: puerto de aprendizaje.
- **Caso real:** Encontrar el puerto que aprendió la MAC del servidor.
- **Filtro / comprobación:** `/interface bridge host print where on-interface="ether2"`

## Detalle de sesiones BGP

```text
/routing bgp session print detail
```

- **Sirve para:** Consulta vecinos BGP establecidos y parámetros negociados.
- **Parámetros / flags:** detail: atributos ampliados; requiere BGP configurado.
- **Caso real:** Encontrar vecino fuera de Established.
- **Filtro / comprobación:** `/routing bgp session print detail`

## SAs IPsec de fase 2

```text
/ip ipsec installed-sa print detail
```

- **Sirve para:** Consulta SAs de cifrado instaladas y contadores.
- **Parámetros / flags:** installed-sa: SAs del plano de datos; detail: propiedades ampliadas.
- **Caso real:** Comprobar si túnel IPsec instaló SAs.
- **Filtro / comprobación:** `/ip ipsec installed-sa print detail`

## Contadores mangle antes del routing

```text
/ip firewall mangle print stats where chain="prerouting"
```

- **Sirve para:** Consulta contadores de reglas prerouting de packet/routing marks.
- **Parámetros / flags:** stats: paquetes/bytes; where: selecciona cadena.
- **Caso real:** Ver si tráfico de policy routing coincide con regla mark.
- **Filtro / comprobación:** `/ip firewall mangle print stats where chain="prerouting"`

## Tráfico en vivo por IP y puerto

```text
/tool torch ether1
```

- **Sirve para:** Observa emisores y tasas de tráfico por interfaz.
- **Parámetros / flags:** ether1: interfaz; vista interactiva; Ctrl+C sale.
- **Caso real:** Encontrar quién satura un uplink; puede omitir tráfico acelerado por hardware.
- **Filtro / comprobación:** `Interactive — do not append Cisco-style pipes.`

> ⚠️ Comandos de diagnóstico sobre funciones opcionales no devuelven información cuando esas funciones no están configuradas. Detén los monitores interactivos al terminar.

**Referencia**: [MikroTik RouterOS](https://help.mikrotik.com/docs/spaces/ROS/pages/328134/Command+Line+Interface)
