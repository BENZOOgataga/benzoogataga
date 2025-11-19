# System Naming Convention

## Updated for the Terraton + Citadel dual-infrastructure era

This document defines the naming rules and inventory structure used across all personal, professional, and infrastructure devices. With the introduction of **SRV-CITADEL**, now fully hosted at the **Pastanetwork datacenter**, the naming convention ensures clarity and consistency between the homelab and production environments.

> **Warning:** Proxmox VE hostnames must never be renamed after initial setup. Renaming can break clustering, storage paths, SSH trust, and network bindings, potentially requiring physical recovery.

---

# 🔤 Hostname Prefix Legend

* **PRS-** — Personal devices (phones, tablets, wearables, audio gear)
* **WRK-** — Workstations (PCs, laptops, productivity machines)
* **SRV-** — Servers (homelab nodes, production nodes, hosted machines)
* **NET-** — Networking equipment (routers, switches, firewalls)

Each hostname is selected to be short, unambiguous, and descriptive of the device’s purpose.

---

# 🖥️ System Inventory

| Category        | Hostname     | Primary Role / Usage                                 | Network Location        |
| --------------- | ------------ | ---------------------------------------------------- | ----------------------- |
| Router          | NET-NEXUS    | Main router and gateway                              | LAN (Home)              |
| Homelab Server  | SRV-TERRATON | Development, staging, internal tools                 | LAN (Home)              |
| Production DC   | SRV-CITADEL  | Datacenter server: production workloads, APIs, games | Pastanetwork Datacenter |
| Main PC         | WRK-AEGIS    | Daily workstation, gaming, creative work             | LAN (Home)              |
| Personal Laptop | WRK-NOMAD    | Portable laptop (work, dev, browsing)                | Variable                |
| iPhone          | PRS-LYNX     | Main phone                                           | N/A                     |
| iPad            | PRS-ATLAS    | Productivity tablet                                  | N/A                     |
| AirPods Pro     | PRS-ECHO     | Portable audio                                       | N/A                     |
| Bose NC700      | PRS-SENTRY   | Noise-cancelling headset                             | N/A                     |
| Apple Watch S3  | PRS-PULSE    | Daily wearable / notifications                       | N/A                     |

> **SRV-CITADEL now exists in production and is fully deployed at Pastanetwork's datacenter.**

---

# 🔄 Distribution of Services

The infrastructure is now split between Terraton (homelab) and Citadel (datacenter). Terraton handles testing, staging, local services, and LAN-dependent workloads. Citadel handles all heavy and uptime-critical roles.

| Service / VM | Role                               | Hosted On              | Notes                            |
| ------------ | ---------------------------------- | ---------------------- | -------------------------------- |
| DYNDNS       | Cloudflare DNS updater             | SRV-TERRATON           | Requires LAN access              |
| GRAFANA      | Dashboards                         | SRV-TERRATON           | Dev environment only             |
| POSTGRESQL   | Internal database                  | SRV-TERRATON           | Local integrations               |
| PNGINX       | Reverse proxy                      | SRV-TERRATON           | Hosts dev websites and tools     |
| PNEXTCLOUD   | Personal cloud                     | SRV-TERRATON           | Stays local by design            |
| POPENVPN     | VPN gateway                        | SRV-TERRATON           | Must remain close to the LAN     |
| LAB          | Testing sandbox                    | SRV-TERRATON           | Temporary isolated workloads     |
| PPTERODACTYL | Game server manager (panel)        | SRV-CITADEL + TERRATON | Prod on Citadel, dev on Terraton |
| SENTINEL     | Uptime Kuma monitoring             | SRV-CITADEL            | Requires datacenter-level uptime |
| APACHE       | Industrium / Flaze SMP web backend | SRV-CITADEL            | Public-facing production service |

> and probably many more not listed as this is dynamic and evolves over the needs of my projects
---

# Summary

The naming convention now reflects a **dual-infrastructure setup**:

* **SRV-TERRATON** → Local homelab, staging, dev, internal tools
* **SRV-CITADEL** → Pastanetwork-hosted datacenter for all production workloads

This clear separation ensures reliability, scalability, and maintainability across all environments while keeping naming clean and predictable.
