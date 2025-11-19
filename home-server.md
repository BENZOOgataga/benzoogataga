# 🏠 Terraton Homelab

## Hybrid backend powering Industrium and LyraStudio

Terraton (**SRV-TERRATON**) began as a personal homelab focused on experimentation and learning. Over time, it evolved into a key part of the backend supporting **Industrium** and **LyraStudio**, while still serving as a flexible environment for development, staging, and internal tooling.

---

# 🧩 System Overview

| Component          | Description                                            |
| ------------------ | ------------------------------------------------------ |
| **Hostname**       | `SRV-TERRATON`                                         |
| **Hypervisor**     | Proxmox VE 8.3.4 (Debian 12 Bookworm)                  |
| **CPU**            | AMD Ryzen 7 5800X (8 cores / 16 threads)               |
| **RAM**            | 64 GB DDR4 3200 MHz                                    |
| **Storage**        | 1 TB Samsung 990 PRO (NVMe) + 224 GB Patriot Burst SSD |
| **GPU**            | NVIDIA GTX 555 *(debug only)*                          |
| **Cooling**        | Air cooling (~74°C under load)                         |
| **Virtualization** | LXC + KVM with bridged networking                      |
| **Network**        | 1 Gbps Realtek NIC + virtual 10 Gbps bridges           |

> The GPU remains in the system solely for local output and emergency debugging.

---

# 🧠 Purpose and Role

Terraton acts as a **hybrid backbone** for both personal and project-oriented needs. Its responsibilities include:

* Development and testing environment for internal tools
* Staging platform for backend components
* Secondary infrastructure for **Industrium** services
* Hosting of lightweight workloads for **LyraStudio** (bots, web utilities, prototypes)
* Reverse proxy, monitoring, and storage layer

With the migration of production workloads to `SRV-CITADEL`, Terraton now prioritizes flexibility, modularity, and rapid iteration.

---

# 📦 Virtual Machines & Containers

Most historical services have been migrated to the datacenter server **SRV-CITADEL**. Terraton now hosts only **light, temporary, or internal** workloads:

* Short-lived development environments
* Sandbox containers for experiments
* Staging versions of internal services
* Supporting infrastructure used during testing cycles

The stack remains intentionally minimal and disposable, ensuring quick rebuilds and low operational overhead.

---

# 🔐 Security & Access

Terraton enforces a simple but effective security model:

* SSH authentication via key pairs only
* Cloudflare protection for exposed services (DNS, SSL, Access rules)
* Proxmox firewall rules + UFW where relevant
* Regular updates across all nodes
* Mandatory snapshots before critical changes

---

# 📈 Monitoring & Backups

Even in its reduced role, Terraton maintains essential observability and backup routines:

* **Uptime Kuma** for service-level availability
* **Prometheus + Grafana** for infrastructure metrics (development mode)
* Daily remote backups over SSH
* Local snapshots for immediate rollbacks

Public status page: `https://status.benzoogataga.com/status/full`

---

# 🔜 Future Direction

As Terraton continues to act as the internal workshop of the ecosystem, **SRV-CITADEL** (hosted at Pastanetwork) carries the production load with:

* Datacenter-grade uptime
* Redundant power and connectivity
* Scalable compute and memory
* Strong separation between production and experimental environments

Both servers complement each other: Terraton for agility and testing, Citadel for reliability and scale.

---

# ✍️ Final Notes

This setup represents years of continuous improvements in infrastructure, game hosting, automation, and backend design. While no longer the primary production node, Terraton remains a reliable and versatile engine behind the experimentation and creativity powering Industrium and LyraStudio.

For discussions or infra-related questions: [benzoogataga](https://guns.lol/benzoogataga) on Discord.
