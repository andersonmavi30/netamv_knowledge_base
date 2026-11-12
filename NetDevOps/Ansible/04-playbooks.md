---
tags: [ansible, cli, netdevops, automation]
validation: not-lab-verified
---

# Playbooks and validation

[🇬🇧 English](04-playbooks.md) · [🇨🇴 Español](04-playbooks.es.md) · [↩ Ansible](README.md)

**Platform:** Ansible CLI / ansible-core 2.x; examples pending lab validation.

## `ansible-playbook -i inventory.ini site.yml --syntax-check`

```bash
ansible-playbook -i inventory.ini site.yml --syntax-check
```

- **Purpose:** Check the playbook syntax without running its tasks.
- **Arguments:** `-i`: choose inventory; `site.yml`: playbook file; `--syntax-check`: parse and validate structure, not runtime behavior.
- **Use case:** Catch YAML/playbook errors before a network change.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible-playbook.html

> Not lab-verified.

## `ansible-playbook -i inventory.ini site.yml --check --diff`

```bash
ansible-playbook -i inventory.ini site.yml --check --diff
```

- **Purpose:** Request a dry run and display predicted changes for modules that support it.
- **Arguments:** `--check`: check mode (not all modules support it); `--diff`: show supported before/after differences; `-i`: inventory.
- **Use case:** Review an intended configuration deployment before execution; never assume zero side effects from unsupported tasks.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible-playbook.html

> Not lab-verified.

## `ansible-playbook -i inventory.ini site.yml --list-hosts`

```bash
ansible-playbook -i inventory.ini site.yml --list-hosts
```

- **Purpose:** Display the hosts targeted by a playbook without executing its tasks.
- **Arguments:** `-i`: inventory; `site.yml`: playbook; `--list-hosts`: show selected target hosts.
- **Use case:** Confirm exactly which routers or switches the playbook would target.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible-playbook.html

> Not lab-verified.

## `ansible-playbook -i inventory.ini site.yml --limit lab-switches --tags backup`

```bash
ansible-playbook -i inventory.ini site.yml --limit lab-switches --tags backup
```

- **Purpose:** Run only backup-tagged tasks for the selected lab group.
- **Arguments:** `-i`: inventory; `--limit lab-switches`: restrict targets; `--tags backup`: select tagged tasks; tasks execute.
- **Use case:** Back up only lab switches after checking playbook target selection.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible-playbook.html

> Not lab-verified.
