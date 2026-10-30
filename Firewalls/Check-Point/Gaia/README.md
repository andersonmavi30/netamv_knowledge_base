# Check Point — Gaia / Security Gateway

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ Check Point](../README.md)

Operational Gaia and Security Gateway reference, distinguishing **Gaia Clish**, **Expert** and security policy managed in SmartConsole.

**Version:** Gaia R8x (verify exact release).

## CLI reference

- [Show & status](01-show.md)
- [Troubleshooting](02-troubleshooting.md)
- [Interfaces & routing](03-interfaces.md)
- [Output filters](04-filters.md)
- [Configuration](05-configuration.md)
- [Firewall operations](06-operations.md)
- [Additional operational checks](07-field-commands.md)
- [Packet capture & debugging](08-packet-debug.md)

**Filters:** in **Expert**, use `clish -c "show ..." | grep ...`; do not assume a Bash pipe is valid at the Gaia Clish prompt.

> Packet capture and debug can affect performance and expose data.
