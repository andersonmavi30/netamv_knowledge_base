# FortiOS — CLI quick reference

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ Fortinet](../README.md)

**Reference version:** FortiOS 7.x. Not a guarantee that every command is present across releases.

- [Additional operations](06-operations.md)

## Index

- [Show / status](01-show.md)
- [Troubleshooting](02-troubleshooting.md)
- [Interface configuration](03-interfaces.md)
- [Output filters](04-filters.md)
- [General configuration](05-configuration.md)
- [🧪 Packet capture / debug](08-packet-debug.md)

## ✅ Check release & syntax

```text
get system status
config firewall address
    ?
```

Identify the precise firmware and use `?` at the appropriate CLI level.

> Illustrative examples pending lab validation. Check the release-specific documentation before production.

- [More operational commands](07-field-commands.md)

- [Five new operational checks](09-operational-checks.md)

- [Five new targeted operational queries](10-targeted-queries.md)

## VDOM, routing and policy notes

- Use `config global` for global scope, and `config vdom` / `edit <VDOM>` for a particular VDOM. `config vdom global` is not how you enter global scope.
- For inter-VDOM links, configure interfaces, routes and policies based on the flows that initiate connections. Policies are stateful: return traffic for an established session does not itself require a reverse policy; create additional policies when new sessions can start in both directions.
- NAT is not inherently required between routed internal networks, but is not universally forbidden; use depends on architecture, overlaps and policy. The management VDOM may originate FortiGuard and other local services; do not assume it is the only internet-connected VDOM.
- `config system virtual-wan-link` is legacy syntax; FortiOS 7.x uses `config system sdwan`.

**References:** https://docs.fortinet.com/document/fortigate/7.0.8/administration-guide/335646/inter-vdom-routing · https://docs.fortinet.com/document/fortigate/7.4.4/administration-guide/256518/configuring-sd-wan-in-the-cli
