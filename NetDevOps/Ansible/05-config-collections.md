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

## `ansible-config view`

```bash
ansible-config view
```

- **Purpose:** Show the currently selected Ansible configuration file contents.
- **Arguments:** `view`: print active configuration; be careful of credentials stored insecurely.
- **Use case:** Inspect unexpected inventory or connection settings in a private terminal.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible-config.html

> Not lab-verified.

## `ansible-config list`

```bash
ansible-config list
```

- **Purpose:** List Ansible configuration options, defaults and environment variable mappings.
- **Arguments:** `list`: display all recognized configuration settings and their documentation; read-only.
- **Use case:** Find the option controlling SSH connection timeout in automation environments.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible-config.html

> Not lab-verified.

## `ansible-galaxy collection verify ansible.netcommon`

```bash
ansible-galaxy collection verify ansible.netcommon
```

- **Purpose:** Verify the installed ansible.netcommon collection against its distribution metadata when available.
- **Arguments:** `collection verify`: compare installed collection to its published artifact; `ansible.netcommon`: collection FQCN; may contact configured Galaxy servers.
- **Use case:** Check collection integrity before using network connection plugins in a lab.
- **Official reference:** https://docs.ansible.com/ansible/latest/cli/ansible-galaxy.html

> Not lab-verified.
