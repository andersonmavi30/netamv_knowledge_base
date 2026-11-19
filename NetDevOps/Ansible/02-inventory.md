---
tags: [ansible, cli, netdevops, automation]
validation: not-lab-verified
---

# Inventory

[🇬🇧 English](02-inventory.md) · [🇨🇴 Español](02-inventory.es.md) · [↩ Ansible](README.md)

**Platform:** Ansible CLI / ansible-core 2.x; examples pending lab validation.

## `ansible-inventory -i inventory.ini --graph`

```bash
ansible-inventory -i inventory.ini --graph
```

- **Purpose:** Visualize groups and host membership in the selected inventory.
- **Arguments:** `-i inventory.ini`: select inventory source; `--graph`: print group/host tree.
- **Use case:** Check which hosts belong to network lab groups before targeting them.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible-inventory.html

> Not lab-verified.

## `ansible-inventory -i inventory.ini --list`

```bash
ansible-inventory -i inventory.ini --list
```

- **Purpose:** Render the inventory as structured JSON, including host and group information.
- **Arguments:** `-i inventory.ini`: inventory source; `--list`: show complete inventory as JSON; may include sensitive variables.
- **Use case:** Diagnose dynamic inventory parsing before running playbooks.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible-inventory.html

> Not lab-verified.

## `ansible-inventory -i inventory.ini --host router1`

```bash
ansible-inventory -i inventory.ini --host router1
```

- **Purpose:** Show all inventory variables for the selected host as JSON.
- **Arguments:** `-i inventory.ini`: inventory; `--host router1`: inspect the named inventory host; output may contain secrets.
- **Use case:** Check how NetBox-derived host variables resolve before connecting to a router.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible-inventory.html

> Not lab-verified.

## `ansible-inventory -i inventory.ini --yaml --list`

```bash
ansible-inventory -i inventory.ini --yaml --list
```

- **Purpose:** Print full inventory as YAML with resolved host and group variables.
- **Arguments:** `-i inventory.ini`: source; `--yaml`: YAML format; `--list`: full inventory. May expose secrets.
- **Use case:** Review inventory host variables before network automation execution.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible-inventory.html

> Not lab-verified.
