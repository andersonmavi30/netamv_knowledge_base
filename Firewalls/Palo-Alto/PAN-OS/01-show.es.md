---
tags: [cli, palo-alto-networks, pan-os, show]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Consultas y estado

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Índice PAN-OS](README.es.md)

**Plataforma:** Palo Alto Networks / PAN-OS · **Compatibilidad:** confirma la versión instalada con `show system info | match sw-version`. Los comandos pueden variar según versión, plataforma, vsys y modo de routing.

## `show system info | match sw-version`

```text
show system info | match sw-version
```

- **Sirve para:** Muestra la versión exacta de PAN-OS.
- **Parámetros:** match: muestra solo líneas que contienen `sw-version`.
- **Ejemplo de uso:** Confirmar compatibilidad antes del mantenimiento.

## `show system info | match hostname`

```text
show system info | match hostname
```

- **Sirve para:** Encuentra el nombre del firewall sin revisar toda la salida.
- **Parámetros:** match hostname: filtra el campo del nombre.
- **Ejemplo de uso:** Confirmar a qué firewall ingresaste por SSH.

## `show interface ethernet1/1`

```text
show interface ethernet1/1
```

- **Sirve para:** Muestra el estado y estadísticas de la interfaz.
- **Parámetros:** ethernet1/1: nombre del puerto físico según modelo.
- **Ejemplo de uso:** Investigar el puerto WAN antes de cambiar.
- **Precaución:** El nombre de interfaz ya limita la consulta; no requiere pipe.

## `show high-availability state | match State`

```text
show high-availability state | match State
```

- **Sirve para:** Muestra líneas de estado de alta disponibilidad.
- **Parámetros:** match State: coincidencia sensible a mayúsculas.
- **Ejemplo de uso:** Verificar estado activo/pasivo al investigar failover.
- **Precaución:** Valida la etiqueta del campo con salida completa según versión.

## `show system route-table | match 0.0.0.0`

```text
show system route-table | match 0.0.0.0
```

- **Sirve para:** Busca ruta por defecto en el plano de administración.
- **Parámetros:** match: filtro de texto; 0.0.0.0: ejemplo de ruta por defecto.
- **Ejemplo de uso:** Diferenciar alcance de gestión de routing de dataplane.

> Referencia breve, pendiente de validación en laboratorio. Comprueba la ayuda contextual `?`, el contexto operational (`>`) y configuration (`#`) antes de ejecutarlos.

**Referencias oficiales:** [Guía 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy) · [Guía 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/get-started-with-the-cli/get-help-on-command-syntax)
