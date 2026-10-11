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

## `show ip interface brief`

```text
show ip interface brief
```

- **Sirve para:** Verifica IP y estado después de la configuración.
- **Parámetros:** brief: resumen.
- **Ejemplo de uso:** Confirmar up/up cuando exista enlace.

- **Filtro práctico:** `show ip interface brief | include GigabitEthernet1/0/1` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.

## `copy running-config startup-config`

```text
copy running-config startup-config
```

- **Sirve para:** Guarda la configuración activa para conservarla tras reinicio.
- **Parámetros:** running-config: origen; startup-config: destino.
- **Ejemplo de uso:** Guardar solo tras verificar los cambios.
- **Precaución:** El guardado sobrescribe la configuración de inicio.

- **Filtro práctico:** `show running-config | section ^interface GigabitEthernet1/0/1` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.


> **Nota:** Referencia rápida, no verificada en laboratorio; confirma sintaxis y permisos en tu modelo y versión.

**Fuente del fabricante:** https://www.cisco.com/c/en/us/td/docs/routers/access/isr1100/software/configuration/xe-17/isr1100-sw-config-xe-17/using_iosxe_software.pdf
