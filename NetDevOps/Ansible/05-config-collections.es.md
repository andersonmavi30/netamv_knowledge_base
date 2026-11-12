---
tags: [ansible, cli, netdevops, automation]
validation: not-lab-verified
---

# Configuración y colecciones

[🇬🇧 English](05-config-collections.md) · [🇨🇴 Español](05-config-collections.es.md) · [↩ Ansible](README.es.md)

**Plataforma:** Ansible CLI / ansible-core 2.x; ejemplos pendientes de prueba en laboratorio.

## `ansible-galaxy collection list`

```bash
ansible-galaxy collection list
```

- **Sirve para:** Listar colecciones Ansible instaladas y sus versiones.
- **Parámetros:** `collection list`: enumera namespaces, colecciones y versiones; no modifica nada.
- **Ejemplo de uso:** Confirmar instalación de `ansible.netcommon` o colecciones del fabricante antes del despliegue.
- **Referencia oficial:** https://docs.ansible.com/ansible/latest/cli/ansible-galaxy.html

> Pendiente de validación en laboratorio.

## `ansible-config dump --only-changed`

```bash
ansible-config dump --only-changed
```

- **Sirve para:** Mostrar únicamente opciones de Ansible modificadas respecto a los valores predeterminados.
- **Parámetros:** `dump`: muestra configuración efectiva; `--only-changed`: omite valores predeterminados.
- **Ejemplo de uso:** Diagnosticar opciones inesperadas de inventario, conexión o callbacks.
- **Referencia oficial:** https://docs.ansible.com/ansible/latest/cli/ansible-config.html

> Pendiente de validación en laboratorio.
