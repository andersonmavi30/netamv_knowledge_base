---
tags: [ansible, cli, netdevops, automation]
validation: not-lab-verified
---

# Playbooks y validación

[🇬🇧 English](04-playbooks.md) · [🇨🇴 Español](04-playbooks.es.md) · [↩ Ansible](README.es.md)

**Plataforma:** Ansible CLI / ansible-core 2.x; ejemplos pendientes de prueba en laboratorio.

## `ansible-playbook -i inventory.ini site.yml --syntax-check`

```bash
ansible-playbook -i inventory.ini site.yml --syntax-check
```

- **Sirve para:** Comprobar la sintaxis del playbook sin ejecutar tareas.
- **Parámetros:** `-i`: inventario; `site.yml`: playbook; `--syntax-check`: valida sintaxis, no comportamiento en ejecución.
- **Ejemplo de uso:** Detectar errores en YAML y playbooks antes de cambios de red.
- **Referencia oficial:** https://docs.ansible.com/ansible/latest/cli/ansible-playbook.html

> Pendiente de validación en laboratorio.
