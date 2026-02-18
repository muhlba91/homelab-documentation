---
title: Infrastructure
icon: server
---

The homelab infrastructure is a multi-site environment consisting of physical and virtual resources managed through Infrastructure as Code (IaC).

## Sites

The infrastructure is distributed across several key locations, combining local physical hardware with cloud-based core services.

### Local Sites (Proxmox)

These sites host the primary computing power for the homelab using physical hardware running Proxmox VE.

| Site | Location | Role | Main Network |
| ---- | -------- | ---- | ------------ |
| **Vienna (VIE)** | Vienna, AT | Primary Home Site | `10.0.0.0/16` |
| **Munich (MUC)** | Munich, DE | Secondary Home Site | `10.1.0.0/16` |

### Cloud Sites (Hetzner)

Core infrastructure services that require high availability or public reachability are hosted on Hetzner Cloud.

| Site | Location | Primary Services |
| ---- | -------- | ---------------- |
| **Core** | Falkenstein (FSN1) | HashiCorp Vault, VPN Gateway (Wireguard), BGP Routing |
| **Mail** | Falkenstein (FSN1) | Postfix, Dovecot, Roundcube, SimpleLogin |

## Server Specifications

### Cloud Infrastructure

- **Core Server**: `cx22` instance (2 vCPU, 4GB RAM) in FSN1.
- **Mail Server**: `cx32` instance (4 vCPU, 8GB RAM) in FSN1.

### Home Clusters

Both Vienna and Munich clusters run on [Talos Linux](https://www.talos.dev/) as virtualized nodes on Proxmox, providing a consistent Kubernetes experience across sites.

## Core Components

### Kubernetes Clusters

Managed via [Talos Linux](https://www.talos.dev/) and provisioned using Pulumi.

- **Vienna Cluster**: Main home cluster.
- **Munich Cluster**: Secondary home cluster.

### Infrastructure Management

- **IaC**: [Pulumi](https://www.pulumi.com/) (Node.js/Go)
- **GitOps**: [Flux CD](https://fluxcd.io/)
- **Secret Management**: [HashiCorp Vault](https://www.vaultproject.io/)
- **Observability**: [Gatus](https://gatus.io/), [InfluxDB](https://www.influxdata.com/)

### Networking

- **VPN / Mesh**: Wireguard (custom mesh), Tailscale.
- **BGP Routing**: Used for interconnectivity between sites.
- **DNS**: Managed via Google Cloud DNS and external-dns.
