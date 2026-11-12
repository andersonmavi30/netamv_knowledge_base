---
tags: [ansible, cli, netdevops, automation]
validation: not-lab-verified
---

# Comandos ad-hoc

[🇬🇧 English](03-ad-hoc.md) · [🇨🇴 Español](03-ad-hoc.es.md) · [↩ Ansible](README.es.md)

**Plataforma:** Ansible CLI / ansible-core 2.x; ejemplos pendientes de prueba en laboratorio.

## `ansible all -i inventory.ini -m ansible.builtin.ping`

```bash
ansible all -i inventory.ini -m ansible.builtin.ping
```

- **Sirve para:** Comprobar conectividad SSH/Python gestionada por Ansible hacia hosts.
- **Parámetros:** `all`: todos los hosts; `-i`: inventario; `-m`: módulo; `ping`: prueba Ansible, no ICMP.
- **Ejemplo de uso:** Validar hosts Linux antes de automatizar; no es un ping ICMP ni prueba estándar para switches sin Python.
- **Referencia oficial:** https://docs.ansible.com/ansible/latest/cli/ansible.html

> Pendiente de validación en laboratorio.
