# Dell Networking

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ Networking](../README.md)

## Operating systems

- [OS6 — mainly N-series switches](OS6/README.md)
- [OS9 — Dell Force10-derived platforms](OS9/README.md)
- [OS10 — supported SmartFabric / PowerSwitch platforms](OS10/README.md)

**NX / N / X:** Dell does not offer one universal CLI for these hardware labels. N and X are hardware series; X-series devices may have web-managed or limited CLI functions. Confirm the exact model and OS (use `show version` where available).

**Packet capture:** there is no universally safe sniffer syntax across OS6, OS9 and OS10. Start with interface counters, logging or supported port mirroring; validate capture tools per device/release.
