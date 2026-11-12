---
tags: [ansible, cli, netdevops, automation]
validation: not-lab-verified
---

# Configuration and collections

[🇬🇧 English](05-config-collections.md) · [🇨🇴 Español](05-config-collections.es.md) · [↩ Ansible](README.md)

**Platform:** Ansible CLI / ansible-core 2.x; examples pending lab validation.

## `ansible-galaxy collection list`

```bash
ansible-galaxy collection list
```

- **Purpose:** List installed Ansible collections and their versions.
- **Arguments:** `collection list`: list installed namespaces, collections and versions; no changes.
- **Use case:** Confirm that `ansible.netcommon` or a vendor collection is installed before deploying network automation.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible-galaxy.html

> Not lab-verified.

## `ansible-config dump --only-changed`

```bash
ansible-config dump --only-changed
```

- **Purpose:** Show only Ansible configuration settings that differ from defaults.
- **Arguments:** `dump`: show effective configuration; `--only-changed`: omit defaults.
- **Use case:** Troubleshoot unexpected inventory, connection or callback settings.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible-config.html

> Not lab-verified.
