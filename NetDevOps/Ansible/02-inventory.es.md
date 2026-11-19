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

## `ansible-inventory -i inventory.ini --list`

```bash
ansible-inventory -i inventory.ini --list
```

- **Sirve para:** Presentar el inventario como JSON estructurado, con hosts y grupos.
- **Parámetros:** `-i inventory.ini`: origen del inventario; `--list`: lista inventario completo en JSON; puede incluir variables sensibles.
- **Ejemplo de uso:** Diagnosticar lectura del inventario dinámico antes de ejecutar playbooks.
- **Referencia oficial:** https://docs.ansible.com/ansible/latest/cli/ansible-inventory.html

> Pendiente de validación en laboratorio.

## `ansible-inventory -i inventory.ini --host router1`

```bash
ansible-inventory -i inventory.ini --host router1
```

- **Sirve para:** Mostrar todas las variables de inventario del host indicado en JSON.
- **Parámetros:** `-i inventory.ini`: inventario; `--host router1`: consulta host de ejemplo; la salida podría revelar secretos.
- **Ejemplo de uso:** Comprobar cómo se resuelven variables de host provenientes de NetBox antes de conectar al router.
- **Referencia oficial:** https://docs.ansible.com/ansible/latest/cli/ansible-inventory.html

> Pendiente de validación en laboratorio.

## `ansible-inventory -i inventory.ini --yaml --list`

```bash
ansible-inventory -i inventory.ini --yaml --list
```

- **Sirve para:** Mostrar inventario completo en YAML con variables resueltas de grupos y hosts.
- **Parámetros:** `-i inventory.ini`: fuente; `--yaml`: formato YAML; `--list`: inventario completo. Puede revelar secretos.
- **Ejemplo de uso:** Revisar variables de hosts antes de automatizar dispositivos.
- **Referencia oficial:** https://docs.ansible.com/ansible/latest/cli/ansible-inventory.html

> Pendiente de validación en laboratorio.
