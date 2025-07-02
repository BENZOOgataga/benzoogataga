# 🏠 My Home Server Setup

This page documents the architecture, usage, and goals of my home server. While originally built for personal homelab experimentation, it's now a core part of the **Industrium** infrastructure.

---

## 🧩 Overview

| Component           | Description                                                                          |
|---------------------|--------------------------------------------------------------------------------------|
| **Hostname**        | `SRV-BASTION`                                                                        |
| **Hypervisor**      | Proxmox VE 8.3.4 (based on Debian 12 Bookworm)                                       |
| **CPU**             | AMD Ryzen 7 5800X (8 cores / 16 threads, Zen 3)                                      |
| **RAM**             | 64 GB DDR4 3200 MHz                                                                  |
| **Storage**         | 1 TB Samsung 990 PRO (NVMe) + 224 GB Patriot Burst SSD                               |
| **GPU**             | NVIDIA GTX 555 *(only used for debug when needed)*                                   |
| **Cooling**         | Air cooling setup (average CPU temp ~74°C under load)                         |
| **Virtualization**  | LXC and KVM-based virtualization with bridged virtual networking                     |
| **Network**         | Realtek 1 Gbps NIC + multiple virtual 10 Gbps interfaces via Proxmox bridges         |

> 🔧 The GPU remains in the system solely because the CPU has no integrated graphics. It's used only for debugging via screen output when needed.

---

## 🧠 Purpose & Use Cases

Originally designed for **lab testing**, the server now powers much of the backend for:

- **Industrium** modded Minecraft server (production)
- Web tools (Nextcloud, Outline, Uptime Kuma, static sites...)
- Discord bots (Lyra Bot dev instance, internal tooling)
- Backup systems and remote access
- Ansible/Pterodactyl provisioning experiments

---

## 📦 Virtual Machines & Containers

All of these are hosted under the node `SRV-BASTION` (see Proxmox summary).

| ID  | Name           | Type | Description / Usage                                                                 |
|-----|----------------|------|-------------------------------------------------------------------------------------|
| 152 | TEMPLATE       | CT   | Base VM / container used for fast deployment                                        |
| 156 | TOLGEE         | CT   | Self-hosted translation platform (inactive)                                         |
| 161 | DYNDNS         | CT   | Dynamic DNS updater linked to Cloudflare                                            |
| 163 | PTERODACTYL    | VM   | Pterodactyl game server manager (panel and daemon)                                  |
| 164 | POSTGRESQL     | CT   | PostgreSQL database used by internal services and bots                              |
| 165 | NGINX          | CT   | Nginx reverse proxy with SSL cert management                                        |
| 166 | NEXTCLOUD      | CT   | Self-hosted file storage and sync platform                                          |
| 167 | SENTINEL       | CT   | Uptime Kuma for monitoring services (internal/public)                               |
| 170 | GRAFANA        | CT   | Grafana dashboards for visualizing Prometheus metrics (inactive)                    |
| 175 | LAB            | CT   | Dev/testing container with restricted network access (isolated from internal VMs)   |
| 176 | APACHE         | CT   | Apache server used by the Industrium Launcher                                       |
| 177 | PROMETHEUS     | CT   | Prometheus server collecting infrastructure and service metrics                     |
| 189 | GHOST          | CT   | Ghost CMS instance for blog/content testing (inactive)                              |
| 190 | CONVERT        | CT   | Used for file/media format conversion or CLI experimentation                        |
| 191 | OUTLINE        | CT   | Internal documentation platform powered by Outline                                  |

> 🧠 Several of these containers are development-grade or used occasionally. The full stack is structured, with Prometheus + Uptime Kuma monitoring them.

---

## 🔐 Security & Access

- All exposed services are protected via **Cloudflare DNS + SSL + Access rules**
- SSH key-based authentication only (MobaXterm)
- Regular Proxmox and Debian package updates
- Router firewall, UFW firewalls
- VM snapshots for rollback before sensitive changes

---

## 📈 Monitoring & Backups

- **Uptime Kuma** monitors public services and endpoints
- **Prometheus + Grafana** stack (dev/testing state)
- Backups stored nightly on a remote machine over SSH
- Local snapshots for quick recovery

> 🔗 You can view uptime and public service status here: [status.benzoogataga.com](https://status.benzoogataga.com)

---

## 🔜 What's Next?

This home server, while reliable, will **not be replaced** but rather repurposed as a dedicated **development and testing platform** for my projects.

A more powerful **production server at [Pastanetwork](https://pastanetwork.com)** (codename: `SRV-CITADEL`) will take over public-facing workloads such as:

- Industrium's production game servers
- Web services and critical infrastructure
- Resource-intensive or uptime-sensitive applications (Uptime Kuma, Outline, ...)

This separation ensures stable operations for users while keeping flexibility and control for development work on the home server.

---

## ✍️ Final Notes

I'm not a profesional sys/netadmin (not yet), but this setup reflects **years of self-taught infrastructure work**, from game servers to web tooling.  
This server is the backbone of many personal and public projects I maintain, and I love iterating on it.

> Want to discuss infra stuff, homelabs, or share advice?  
> Feel free to contact me on [Discord](https://guns.lol/benzoogataga)
