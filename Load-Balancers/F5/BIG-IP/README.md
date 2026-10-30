# F5 BIG-IP — TMOS / LTM

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ F5](../README.md)

F5 BIG-IP command reference covering virtual servers, pools, connections, networking and capture. Commands use the `tmsh` prefix from Bash; omit the prefix in the tmsh shell.

## Topics

- [Show & status](01-show.md)
- [Troubleshooting](02-troubleshooting.md)
- [Networking & routes](03-interfaces.md)
- [Output filters](04-filters.md)
- [Configuration](05-configuration.md)
- [LTM operations](06-operations.md)
- [Additional operational checks](07-field-commands.md)
- [Packet capture & diagnostics](08-packet-debug.md)

**Filtering:** `tmsh list ltm virtual | grep -i lab` works with tmsh output filtering.

> Verify release, partition (`/Common`) and privileges before modifying services.
