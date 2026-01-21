# 🏠 SRV-TERRATON - Home Server

> **Flexible infrastructure backend** for **Industrium** and **Altitude Interactive**, doubling as a personal development lab.

---

## 🖥️ Hardware Specs

| Spec | Details |
|------|---------|
| **Hostname** | `SRV-TERRATON` |
| **Hypervisor** | Proxmox VE 8.3.4 (Debian 12 Bookworm) |
| **CPU** | AMD Ryzen 7 5800X (8C/16T) |
| **RAM** | 64 GB DDR4 3200 MHz |
| **Storage** | 1 TB Samsung 990 PRO (NVMe) + 224 GB Patriot Burst SSD |
| **GPU** | NVIDIA GTX 555 (debug only) |
| **Cooling** | Air-cooled (~74°C under load) |
| **Network** | 1 Gbps Realtek NIC + Virtual 10 Gbps bridges |

---

## 🎯 What Does It Do?

SRV-TERRATON serves as a **hybrid backend** supporting both experimentation and production needs:

- 🧪 **Development & Testing** - Sandbox environments for new tools and services
- 📦 **Staging Platform** - Pre-production testing before datacenter deployment
- 🎮 **Industrium Services** - Secondary backend components (alongside SRV-CITADEL)
- 🤖 **Altitude Interactive** - Lightweight hosting for bots, utilities, and prototypes
- 🔄 **Reverse Proxy & Monitoring** - Internal infrastructure layer

---

## 🏗️ Current Workloads

Most production services have migrated to **SRV-CITADEL** (datacenter hosted). SRV-TERRATON now focuses on **lightweight, temporary, and internal** workloads:

- Short-lived development environments
- Experimental sandbox containers
- Staging versions of backend services
- Infrastructure tooling during test cycles

This intentional minimalism ensures quick rebuilds and low maintenance overhead.

---

## 🔒 Security & Reliability

**Access & Authentication:**
- SSH key-based authentication only
- Cloudflare protection for exposed services (DNS, SSL, firewall rules)
- Proxmox firewall + UFW rules per container
- Regular security updates

**Monitoring & Backups:**
- **Uptime Kuma** for service availability tracking
- **Prometheus + Grafana** for metrics (development mode)
- Daily remote backups via SSH
- Local VM snapshots for instant rollbacks

📊 **Public Status:** [status.benzoogataga.com](https://status.benzoogataga.com)

---

## 🚀 SRV-TERRATON + SRV-CITADEL

SRV-TERRATON works alongside **SRV-CITADEL**, a professional datacenter server (T3 Pastanetwork):

| | SRV-TERRATON | SRV-CITADEL |
|---|----------|-------------|
| **Role** | Dev, staging & experimentation | Primary production backend |
| **Location** | Home lab | Pastanetwork T3 Datacenter |
| **Uptime SLA** | Development-grade | Enterprise-grade |
| **Primary Use** | Testing, iteration, internal tooling | Live Industrium & Altitude Interactive services |

**Result:** Separation of concerns with rapid iteration at home and proven reliability in the datacenter.

---

## 📝 Final Notes

SRV-TERRATON has evolved from a personal hobby lab into a critical piece of the Industrium & Altitude Interactive infrastructure. While no longer primary production, it remains essential for rapid iteration, debugging, and internal tool development.

**Questions?** Hit me up on [Discord](https://guns.lol/benzoogataga) or email [contact@benzoogataga.com](mailto:contact@benzoogataga.com)
