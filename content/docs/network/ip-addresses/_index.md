---
title: IP Addresses
weight: 1
next: vienna
---

The homelab uses the `10.0.0.0/8` private address space for internal networking.

Each site is allocated a specific `/16` block. To maintain consistency, subnets within these blocks follow a standardized pattern across all locations.

## Site Allocations

| Site | IPv4 Range | IPv6 Range |
| ---- | ---------- | ---------- |
| [Vienna (VIE)](vienna) | `10.0.0.0/16` | `2a01:aea0:dd3:25a::/64` |
| [Munich (MUC)](munich) | `10.1.0.0/16` | `fd40:2e3:42a::/64` |

## Cluster Networks

Standardized CIDRs for Kubernetes networking across sites:

| Description | Vienna (VIE) | Munich (MUC) |
| ----------- | ------------ | ------------ |
| POD CIDR | `10.101.0.0/16` | `10.102.0.0/16` |
| Service CIDR | `10.105.0.0/16` | `10.106.0.0/16` |
| Load Balancer CIDR | `10.111.0.0/16` | `10.112.0.0/16` |

## General Allocations

For details on how individual IPs are assigned within a site's main CIDR (e.g., for routers, switches, and servers), see the [Main CIDR / General Use](main-cidr) page.
