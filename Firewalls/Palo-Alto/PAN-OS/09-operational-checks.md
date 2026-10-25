---
tags: [cli, palo-alto-networks, pan-os, operations]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Additional operational checks

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Index](README.md)

**Compatibility:** PAN-OS. Verify installed release and on-device `?` help.

## `show jobs all | match FIN`

```text
show jobs all | match FIN
```

- **Purpose:** Find completed commit and download jobs without reading every entry.
- **Arguments:** jobs all: job history; match FIN: matching completion status text.
- **Use case:** Track the result of a configuration commit.

## `show session id 12345`

```text
show session id 12345
```

- **Purpose:** Display detailed session state for an exact session ID.
- **Arguments:** id 12345: session identifier discovered in session table.
- **Use case:** Check source, destination and session state after investigating a client.

## `show user ip-user-mapping ip 192.0.2.10`

```text
show user ip-user-mapping ip 192.0.2.10
```

- **Purpose:** Check the user mapped to a particular source IP.
- **Arguments:** ip: exact address; User-ID must be configured and populated.
- **Use case:** Investigate user-based policy match failures.

## `show system disk-space | match /opt/panlogs`

```text
show system disk-space | match /opt/panlogs
```

- **Purpose:** Focus disk-space output on the log partition.
- **Arguments:** match: text filtering; partition labels vary by platform.
- **Use case:** Check capacity when traffic logs stop appearing.

## `show high-availability all | match peer`

```text
show high-availability all | match peer
```

- **Purpose:** Find peer-related fields in HA diagnostics.
- **Arguments:** all: expanded HA information; match peer: targeted text.
- **Use case:** Check peer details during failover troubleshooting.

> Not lab-verified. Some features require configuration, license or privileges.

**Official docs:** https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy
