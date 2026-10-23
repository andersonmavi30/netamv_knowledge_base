---
tags: [cli, palo-alto-networks, pan-os, show]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# 🔎 Consultas y estado

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Índice PAN-OS](README.es.md)

**Compatibilidad:** PAN-OS (revisar versión exacta con `show system info | match sw-version`). Los comandos pueden variar según versión, plataforma, vsys y modo de routing.

## Identificar versión PAN-OS

```text
show system info | match sw-version
```

- **Sirve para:** Muestra la versión exacta de PAN-OS.
- **Parámetros y filtros:** match: muestra solo líneas que contienen `sw-version`.
- **Caso real:** Confirmar compatibilidad antes del mantenimiento.

## Buscar hostname

```text
show system info | match hostname
```

- **Sirve para:** Encuentra el nombre del firewall sin revisar toda la salida.
- **Parámetros y filtros:** match hostname: filtra el campo del nombre.
- **Caso real:** Confirmar a qué firewall ingresaste por SSH.

## Consultar interfaz física

```text
show interface ethernet1/1
```

- **Sirve para:** Muestra el estado y estadísticas de la interfaz.
- **Parámetros y filtros:** ethernet1/1: nombre del puerto físico según modelo.
- **Caso real:** Investigar el puerto WAN antes de cambiar.
- **Precaución:** El nombre de interfaz ya limita la consulta; no requiere pipe.

## Comprobar HA

```text
show high-availability state | match State
```

- **Sirve para:** Muestra líneas de estado de alta disponibilidad.
- **Parámetros y filtros:** match State: coincidencia sensible a mayúsculas.
- **Caso real:** Verificar estado activo/pasivo al investigar failover.
- **Precaución:** Valida la etiqueta del campo con salida completa según versión.

## Revisar rutas de gestión

```text
show system route-table | match 0.0.0.0
```

- **Sirve para:** Busca ruta por defecto en el plano de administración.
- **Parámetros y filtros:** match: filtro de texto; 0.0.0.0: ejemplo de ruta por defecto.
- **Caso real:** Diferenciar alcance de gestión de routing de dataplane.

> Ejemplos orientativos pendientes de validación en laboratorio. Comprueba la ayuda contextual `?`, el contexto operational (`>`) y configuration (`#`) antes de ejecutarlos.

**Referencias oficiales:** [Guía 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy) · [Guía 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/get-started-with-the-cli/get-help-on-command-syntax)
