# 🌐 NETAMV Knowledge Base

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md)

**A practical, bilingual IT / NetDevOps CLI knowledge base.**
Concise commands, commonly used options, short examples and troubleshooting notes — organized by domain, vendor and operating system.

## 📚 Browse

| Domain | Vendor | Operating system | Quick reference |
|---|---|---|---|
| 🛡️ [Firewalls](Firewalls/README.md) | [Fortinet](Firewalls/Fortinet/README.md) | FortiOS | [Show](Firewalls/Fortinet/FortiOS/01-show.md) · [Troubleshooting](Firewalls/Fortinet/FortiOS/02-troubleshooting.md) · [Interfaces](Firewalls/Fortinet/FortiOS/03-interfaces.md) · [Filters](Firewalls/Fortinet/FortiOS/04-filters.md) |
| 🌐 [Networking](Networking/README.md) | [Cisco](Networking/Cisco/README.md) | IOS XE | [Show](Networking/Cisco/IOS-XE/01-show.md) · [Troubleshooting](Networking/Cisco/IOS-XE/02-troubleshooting.md) · [Interfaces](Networking/Cisco/IOS-XE/03-interfaces.md) · [Filters](Networking/Cisco/IOS-XE/04-filters.md) |

**Current scope:** Fortinet/FortiOS and Cisco/IOS XE. Other technologies will be added progressively.

## 🧭 How to use

- Find a vendor and OS, then choose **Show**, **Troubleshooting**, **Interfaces** or **Filters**.
- Each reference is short: **command → purpose → common arguments → example**.
- English files end in \`.md\`; Spanish translations use \`.es.md\`.
- **Version notes describe intended scope, not certification of compatibility.** Verify syntax against the exact firmware/software release before using it.
- Sample IPs in the documentation use reserved TEST-NET addresses; never paste lab configuration into production without reviewing impact.
- Do not commit passwords, tokens, private configuration or customer information.

## 🪨 Use with Obsidian

1. Clone this GitHub repository to your computer.
2. Open the cloned directory as an **Obsidian vault**.
3. Optionally install the community **Obsidian Git** plugin to configure pull/push.
4. Keep local Obsidian settings out of Git (see [\`.gitignore\`](.gitignore)).

**No MCP server or paid OpenAI API is required** for GitHub ↔ Obsidian synchronization. MCP can be added independently later.

## ✍️ Contributing

Use the [English](Templates/command-reference.md) or [Spanish](Templates/command-reference.es.md) reference template. Keep examples safe, short and vendor/OS-specific. Include the applicable version or mark it as **not yet validated**.

## 📄 License

Documentation © 2026 Anderson Martínez Virviescas, distributed under [Creative Commons Attribution 4.0 International](LICENSE) (CC BY 4.0). Third-party trademarks remain their owners' property.
