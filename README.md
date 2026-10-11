# 🌐 NETAMV Knowledge Base

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md)

**A practical, bilingual IT / NetDevOps CLI knowledge base.**
Concise commands, commonly used options, short examples and troubleshooting notes — organized by domain, vendor and operating system.

## 📚 Browse

| Domain | Vendor | Operating system | Quick reference |
|---|---|---|---|
| 🛡️ [Firewalls](Firewalls/README.md) | [Fortinet](Firewalls/Fortinet/README.md) | FortiOS | [Show](Firewalls/Fortinet/FortiOS/01-show.md) · [Troubleshooting](Firewalls/Fortinet/FortiOS/02-troubleshooting.md) · [Interfaces](Firewalls/Fortinet/FortiOS/03-interfaces.md) · [Filters](Firewalls/Fortinet/FortiOS/04-filters.md) |
| 🌐 [Networking](Networking/README.md) | [Cisco](Networking/Cisco/README.md) | IOS XE | [Show](Networking/Cisco/IOS-XE/01-show.md) · [Troubleshooting](Networking/Cisco/IOS-XE/02-troubleshooting.md) · [Interfaces](Networking/Cisco/IOS-XE/03-interfaces.md) · [Filters](Networking/Cisco/IOS-XE/04-filters.md) |
| 🌐 [Networking](Networking/README.md) | [Cisco](Networking/Cisco/README.md) | IOS 15.x | [Show](Networking/Cisco/IOS/01-show.md) · [Troubleshooting](Networking/Cisco/IOS/02-troubleshooting.md) · [Configuration](Networking/Cisco/IOS/05-configuration.md) |

**Current scope:** Fortinet/FortiOS 7.x, Cisco classic IOS and IOS XE. Other technologies will be added progressively.

## 🧭 How to use

- Find a vendor and OS, then choose **Show**, **Troubleshooting**, **Interfaces** or **Filters**.
- Each reference is short: **command → purpose → common arguments → example**.
- English files end in \`.md\`; Spanish translations use \`.es.md\`.
- **Version notes describe intended scope, not certification of compatibility.** Verify syntax against the exact firmware/software release before using it.
- Sample IPs in the documentation use reserved TEST-NET addresses; never paste lab configuration into production without reviewing impact.
- Do not commit passwords, tokens, private configuration or customer information.

## ✍️ Contributing

Use the [English](Templates/command-reference.md) or [Spanish](Templates/command-reference.es.md) reference template. Keep examples safe, short and vendor/OS-specific. Include the applicable version or mark it as **not yet validated**.

## 📄 License

Documentation © 2026 Anderson Martínez Virviescas, distributed under [Creative Commons Attribution 4.0 International](LICENSE) (CC BY 4.0). Third-party trademarks remain their owners' property.
