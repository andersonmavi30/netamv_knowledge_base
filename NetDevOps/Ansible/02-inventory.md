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
