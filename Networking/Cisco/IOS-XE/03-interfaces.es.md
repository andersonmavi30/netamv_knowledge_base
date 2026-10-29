---
tags: [cli, cisco, ios-xe, interfaces]
vendor: Cisco
os: "IOS XE"
validation: not-lab-verified
---

# 🔌 Configuración de interfaces

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Cisco](../README.es.md)

**Plataforma:** Cisco / IOS XE · **Compatibilidad:** Cisco IOS XE 17.x (depende del modelo; valida tu versión).

## `show running-config interface GigabitEthernet1/0/1`

```text
show running-config interface GigabitEthernet1/0/1
```

- **Sirve para:** Revisa la configuración actual de un puerto.
- **Parámetros:** La identificación de interfaz cambia según modelo.
- **Ejemplo de uso:** Comparar antes de aplicar cambios.

- **Filtro práctico:** `show running-config | section ^interface GigabitEthernet1/0/1` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.

## `configure terminal`

```text
configure terminal
interface GigabitEthernet1/0/1
 description LAB-UPLINK
 no shutdown
end
```

- **Sirve para:** Define la descripción de la interfaz y la habilita.
- **Parámetros:** configure terminal: modo de configuración; interface: selecciona puerto; description: etiqueta; no shutdown: habilita; end: salir.
- **Ejemplo de uso:** Habilitar un enlace de laboratorio.
- **Precaución:** Habilitar un puerto cambia conectividad. Verifica antes su función.

- **Filtro práctico:** `show ip interface brief | include GigabitEthernet1/0/1` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.

## `show interfaces description | include UPLINK`

```text
show interfaces description | include UPLINK
```

- **Sirve para:** Busca descripciones y estado operativo de los uplinks.
- **Parámetros:** description: resumen de interfaz, estado y etiqueta; include: búsqueda textual.
- **Ejemplo de uso:** Identificar el enlace UPLINK antes de revisar errores físicos.
- **Referencia:** [Documentación del fabricante](https://www.cisco.com/c/en/us/td/docs/switches/lan/catalyst4500/XE3-11-0E/command/reference/xe-311-cmd/show1.html)

> **Nota:** Referencia rápida, no verificada en laboratorio; confirma sintaxis y permisos en tu modelo y versión.

**Fuente del fabricante:** https://www.cisco.com/c/en/us/td/docs/routers/access/isr1100/software/configuration/xe-17/isr1100-sw-config-xe-17/using_iosxe_software.pdf
