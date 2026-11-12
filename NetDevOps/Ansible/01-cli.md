---
tags: [ansible, cli, netdevops, automation]
validation: not-lab-verified
---

# CLI and documentation

[🇬🇧 English](01-cli.md) · [🇨🇴 Español](01-cli.es.md) · [↩ Ansible](README.md)

**Platform:** Ansible CLI / ansible-core 2.x; examples pending lab validation.

## `ansible --version`

```bash
ansible --version
```

- **Purpose:** Display Ansible and Python versions, configuration file and executable paths.
- **Arguments:** `--version`: print version/environment details; read-only.
- **Use case:** Check versions before executing a lab playbook.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible.html

> Not lab-verified.

## `ansible-doc ansible.builtin.copy`

```bash
ansible-doc ansible.builtin.copy
```

- **Purpose:** Display the built-in copy module documentation and examples.
- **Arguments:** `ansible-doc`: module documentation; `ansible.builtin.copy`: fully qualified module name.
- **Use case:** Inspect expected parameters before writing a file deployment task.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible-doc.html

> Not lab-verified.
