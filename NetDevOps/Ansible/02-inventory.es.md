---
tags: [ansible, cli, netdevops, automation]
validation: not-lab-verified
---

# Inventarios

[🇬🇧 English](02-inventory.md) · [🇨🇴 Español](02-inventory.es.md) · [↩ Ansible](README.es.md)

**Plataforma:** Ansible CLI / ansible-core 2.x; ejemplos pendientes de prueba en laboratorio.

## `ansible-inventory -i inventory.ini --graph`

```bash
ansible-inventory -i inventory.ini --graph
```

- **Sirve para:** Visualizar grupos y hosts presentes en el inventario indicado.
- **Parámetros:** `-i inventory.ini`: selecciona inventario; `--graph`: presenta árbol de grupos/hosts.
- **Ejemplo de uso:** Comprobar los hosts de grupos de laboratorio antes de ejecutarlos.
- **Referencia oficial:** https://docs.ansible.com/ansible/latest/cli/ansible-inventory.html

> Pendiente de validación en laboratorio.
