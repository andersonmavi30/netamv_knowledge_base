---
tags: [ansible, cli, netdevops, automation]
validation: not-lab-verified
---

# Ad-hoc commands

[🇬🇧 English](03-ad-hoc.md) · [🇨🇴 Español](03-ad-hoc.es.md) · [↩ Ansible](README.md)

**Platform:** Ansible CLI / ansible-core 2.x; examples pending lab validation.

## `ansible all -i inventory.ini -m ansible.builtin.ping`

```bash
ansible all -i inventory.ini -m ansible.builtin.ping
```

- **Purpose:** Test Ansible-managed SSH/Python connectivity to inventory hosts.
- **Arguments:** `all`: all inventory hosts; `-i`: inventory; `-m`: module; `ping`: module connectivity test (not ICMP).
- **Use case:** Verify Linux hosts before running automation; not suitable for network devices without Python.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible.html

> Not lab-verified.
