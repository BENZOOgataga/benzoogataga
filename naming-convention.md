# System Naming Convention

This document lists all devices used personally and professionally by the owner. Each device is identified by a unique hostname following a strict naming convention to ensure absolute clarity, network coherence, and ease of management in technical or domestic environments.

> **Important:** Never rename Proxmox VE hosts after their initial configuration. Doing so can cause critical service disruptions or even loss of network access. This rule was established after a real incident that required physical intervention to recover from an unsuccessful renaming.

---

## Hostname Prefix Legend:

- **PRS-** : Personal - Personal, mobile, or portable devices (smartphones, tablets, accessories).
- **WRK-** : Workstation - Computers dedicated to work or extensive daily usage.
- **SRV-** : Server - Machines dedicated to networking tasks, infrastructure, hosting, or production.
- **NET-** : Network - Fixed network equipment (routers, switches, firewalls, etc.).

Each name is carefully chosen to reflect the role and nature of the device while maintaining a consistent and clean aesthetic.

---

## System Inventory

| Category            | Hostname    | Primary Role / Usage                             | Current Network |
|---------------------|-------------|--------------------------------------------------|-----------------|
| Network Router      | NET-NEXUS   | Main router, local network gateway               | LAN (HOST)      |
| Local Server        | SRV-BASTION | Development, local hosting, various services     | LAN             |
| Remote Server       | SRV-CITADEL | Datacenter, heavy production, game servers, etc. | DATACENTER      |
| Main PC             | WRK-AEGIS   | Fixed workstation, multitasking, creative tasks  | LAN             |
| Personal Laptop     | WRK-NOMAD   | Versatile laptop (work, dev, gaming, browsing)   | N/A             |
| iPhone              | PRS-LYNX    | Main mobile device, communication, entertainment | N/A             |
| iPad                | PRS-ATLAS   | Productivity on-the-go, reading, games, leisure  | N/A             |
| AirPods Pro 2       | PRS-ECHO    | Portable audio, calls, discrete listening        | N/A             |
| Bose NC700          | PRS-SENTRY  | Noise-cancelling headset, focus                  | N/A             |
| Apple Watch S3      | PRS-PULSE   | Health tracking, notifications, wrist assistant  | N/A             |

*Note: SRV-CITADEL is currently planned but does not yet exist.*

---

## Distribution of services between SRV-BASTION and SRV-CITADEL

| VM/CT Name   | Type      | Service / Role                    | Hosted On                 | Notes                                        |
|--------------|-----------|-----------------------------------|---------------------------|----------------------------------------------|
| DYNDNS       | LXC (161) | DNS updater                       | SRV-BASTION               | Requires LAN                                 |
| TOLGEE       | LXC (156) | Localization service              | SRV-BASTION               | Lightweight use, local dev                   |
| GRAFANA      | LXC (170) | Monitoring                        | SRV-BASTION               | Low resource usage                           |
| POSTGRESQL   | VM (164)  | Database                          | SRV-BASTION               | Local dependencies                           |
| PNGINX        | VM (165)  | Reverse proxy                     | SRV-BASTION               | Complex migration, hosts several sites       |
| PNEXTCLOUD   | VM (168)  | Personal cloud                    | SRV-BASTION               | Controlled load, no expected overload        |
| POPENVPN     | VM (162)  | VPN access to local network       | SRV-BASTION               | Must remain close to LAN                     |
| LAB          | VM (175)  | Testing environment               | SRV-BASTION               | Internal use only                            |
| PPTERODACTYL | VM (163)  | Game server management panel      | SRV-CITADEL & SRV-BASTION | Production on CITADEL, dev on BASTION        |
| SENTINEL     | VM (169)  | Uptime Kuma monitoring            | SRV-CITADEL (planned)     | Better uptime expected on CITADEL            |
| APACHE       | VM (176)  | Flaze SMP launcher web service    | SRV-CITADEL (planned)     | Web production, relevant on CITADEL          |
