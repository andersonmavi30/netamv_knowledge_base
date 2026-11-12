---
tags: [ansible, cli, netdevops, automation]
validation: not-lab-verified
---

# CLI y documentación

[🇬🇧 English](01-cli.md) · [🇨🇴 Español](01-cli.es.md) · [↩ Ansible](README.es.md)

**Plataforma:** Ansible CLI / ansible-core 2.x; ejemplos pendientes de prueba en laboratorio.

## `ansible --version`

```bash
ansible --version
```

- **Sirve para:** Mostrar versión de Ansible, Python, configuración y rutas utilizadas.
- **Parámetros:** `--version`: muestra versión y detalles del entorno; no modifica equipos.
- **Ejemplo de uso:** Comprobar versiones antes de ejecutar un playbook en el laboratorio.
- **Referencia oficial:** https://docs.ansible.com/ansible/latest/cli/ansible.html

> Pendiente de validación en laboratorio.

## `ansible-doc ansible.builtin.copy`

```bash
ansible-doc ansible.builtin.copy
```

- **Sirve para:** Mostrar documentación y ejemplos del módulo copy.
- **Parámetros:** `ansible-doc`: documentación; `ansible.builtin.copy`: nombre completo del módulo.
- **Ejemplo de uso:** Consultar parámetros antes de crear una tarea para copiar archivos.
- **Referencia oficial:** https://docs.ansible.com/ansible/latest/cli/ansible-doc.html

> Pendiente de validación en laboratorio.
