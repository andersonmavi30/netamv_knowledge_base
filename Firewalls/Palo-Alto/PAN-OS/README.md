# Palo Alto Networks — PAN-OS

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ Vendor](../README.md)

Operational reference for Palo Alto Networks NGFW. Use `>` for operations, `configure` (`#`) for candidate changes and a reviewed `commit` to apply.

**Compatibility:** PAN-OS generic (verify version and platform).

```text
show system info | match sw-version
show system info | match hostname
```

## CLI topics

- [Show & status](01-show.md)
- [Troubleshooting](02-troubleshooting.md)
- [Interfaces & routing](03-interfaces.md)
- [Output filters & targeted lookups](04-filters.md)
- [Configuration examples](05-configuration.md)
- [VPN, policy & operational checks](06-operations.md)
- [Additional field checks](07-field-commands.md)
- [Packet capture & debug](08-packet-debug.md)
- [Additional operational checks](09-operational-checks.md)

> Do not assume Fortinet/Cisco `grep` or `include` syntax. PAN-OS uses `| match`, `| except` and command-specific filters.

**Safety:** packet capture consumes resources and commits may apply pending changes.

- [Ten focused operational commands](10-targeted-queries.md)
