# 📋 System Naming Convention

> Consistent, descriptive naming for all devices across personal, professional, and infrastructure environments.

---

## 🏷️ Prefix Legend

| Prefix | Category | Examples |
|--------|----------|----------|
| **PRS-** | Personal devices | Phones, tablets, wearables, audio |
| **WRK-** | Workstations | PCs, laptops, development machines |
| **SRV-** | Servers | Homelab nodes, production nodes, hosted machines |
| **NET-** | Network equipment | Routers, switches, firewalls |

Each hostname is **short, unambiguous, and descriptive** of its primary purpose.

⚠️ **Important:** Proxmox VE hostnames must never be renamed after initial setup. Renaming breaks clustering, storage paths, SSH trust, and network bindings, potentially requiring physical recovery.

---

## 🖥️ Device Inventory

| Device | Hostname | Role | Location |
|--------|----------|------|----------|
| Main Router | NET-NEXUS | Gateway & main network | LAN (Home) |
| Homelab Server | **SRV-TERRATON** | Development, staging, internal tools | LAN (Home) |
| Production Server | **SRV-CITADEL** | Production workloads, APIs, games | Pastanetwork T3 Datacenter |
| Daily PC | WRK-AEGIS | Workstation, gaming, creative work | LAN (Home) |
| Laptop | WRK-NOMAD | Portable work & dev machine | Variable |
| iPhone | PRS-LYNX | Main phone | N/A |
| iPad | PRS-ATLAS | Productivity tablet | N/A |
| AirPods Pro | PRS-ECHO | Portable audio | N/A |
| Bose Headset | PRS-SENTRY | Noise-cancelling headphones | N/A |
| Apple Watch | PRS-PULSE | Wearable notifications | N/A |

---

## 🚀 Infrastructure Setup

**Dual-Server Architecture:**
- **SRV-TERRATON** (Homelab) - Agile development & staging
- **SRV-CITADEL** (Datacenter) - Reliable production workloads

This separation ensures **rapid iteration without sacrificing uptime or reliability**.

---

## 📦 Service Distribution

| Service | Purpose | Primary Host | Notes |
|---------|---------|--------------|-------|
| **DYNDNS** | Cloudflare DNS updates | SRV-TERRATON | Requires local LAN access |
| **GRAFANA** | Infrastructure dashboards | SRV-TERRATON | Development-only metrics |
| **POSTGRESQL** | Internal databases | SRV-TERRATON | Local integrations |
| **PNGINX** | Reverse proxy | SRV-TERRATON | Dev websites & utilities |
| **PNEXTCLOUD** | Personal cloud storage | SRV-TERRATON | Stays local by design |
| **POPENVPN** | VPN gateway | SRV-TERRATON | Must remain LAN-local |
| **LAB** | Testing sandbox | SRV-TERRATON | Temporary experiments |
| **PPTERODACTYL** | Game server manager | SRV-CITADEL + SRV-TERRATON | Prod on SRV-CITADEL, dev on SRV-TERRATON |
| **SENTINEL** | Uptime monitoring (Kuma) | SRV-CITADEL | Requires datacenter uptime |
| **APACHE** | Industrium web backend | SRV-CITADEL | Public-facing production |

> *More services exist but aren't listed as the stack is dynamic and evolves with project needs.*

---

## 📝 Summary

This naming convention creates a **clear, scalable infrastructure** that's easy to manage and understand:

✅ **Consistent prefixes** for quick device identification  
✅ **Logical separation** between homelab and production  
✅ **Future-proof** as new systems are added  
✅ **Easy to remember** with descriptive codenames  

The dual-server setup balances **experimentation** (SRV-TERRATON) with **reliability** (SRV-CITADEL).
