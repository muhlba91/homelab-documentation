---
title: Core Infrastructure (CORE)
weight: 5
---

The Core Infrastructure site serves as the central hub for the homelab's management and interconnectivity.

## Network Topology

- **VPC CIDR**: `10.21.0.0/16`
- **Primary Subnet**: `10.21.0.0/24`

## Central Services

- **HashiCorp Vault**: Centralized secret management and PKI.
- **VPN Gateway**: Wireguard-based access for users and site-to-site mesh.
- **BGP Router**: Manages routing between the various sites and cloud resources.
