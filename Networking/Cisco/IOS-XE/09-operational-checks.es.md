---
tags: [cli, netdevops, operational-checks]
validation: not-lab-verified
---

# 🧭 Verificaciones operativas — ampliación · Cisco IOS XE

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** IOS XE 17.x (features vary by model). Los comandos no se han ejecutado en equipos; confirma la sintaxis con `?` y la documentación de tu versión.

## Asociaciones NTP

```text
show ntp associations
```

- **Sirve para:** Consulta servidores NTP y selección de sincronización.
- **Parámetros / flags:** associations: asociaciones NTP configuradas y aprendidas.
- **Caso real:** Revisar hora antes de correlacionar syslogs.
- **Filtro / comprobación:** `show ntp associations`

## Contadores QoS por interfaz

```text
show policy-map interface GigabitEthernet1/0/1
```

- **Sirve para:** Revisa contadores por clase y descartes de políticas QoS.
- **Parámetros / flags:** interface: puerto; requiere política QoS aplicada.
- **Caso real:** Encontrar drops por clase QoS de WAN.
- **Filtro / comprobación:** `show policy-map interface GigabitEthernet1/0/1 | include drop|packets`

## Asignaciones DHCP

```text
show ip dhcp binding
```

- **Sirve para:** Muestra asociaciones IP-cliente si el equipo funciona como servidor DHCP.
- **Parámetros / flags:** binding: concesiones del servidor DHCP.
- **Caso real:** Identificar IP asignada a un cliente.
- **Filtro / comprobación:** `show ip dhcp binding | include 192.0.2`

## Asociaciones VPN IKEv2

```text
show crypto ikev2 sa
```

- **Sirve para:** Consulta estado de asociaciones IKEv2 en routers compatibles.
- **Parámetros / flags:** ikev2 sa: SAs de control negociadas; depende del equipo.
- **Caso real:** Encontrar túnel cuya negociación IKEv2 no terminó.
- **Filtro / comprobación:** `show crypto ikev2 sa | include READY|IN-NEG`

## Recursos del plano de control

```text
show platform software status control-processor brief
```

- **Sirve para:** Consulta CPU y memoria del procesador de control donde aplique.
- **Parámetros / flags:** brief: estado resumido; depende de plataforma.
- **Caso real:** Verificar sobrecarga de procesos de control/gestión.
- **Filtro / comprobación:** `show platform software status control-processor brief`

> ⚠️ Comandos de diagnóstico sobre funciones opcionales no devuelven información cuando esas funciones no están configuradas. Detén los monitores interactivos al terminar.

**Referencia**: [Cisco IOS XE](https://www.cisco.com/c/en/us/support/ios-nx-os-software/ios-xe/products-command-reference-list.html)
