---
title: BGP
weight: 2
next: peering
---

The infrastructure uses the Border Gateway Protocol (BGP) to manage routing between all sites and to announce public routes.

## Routing Architecture

- **Internal BGP (iBGP)**: Used within sites to distribute internal routes.
- **External BGP (eBGP)**: Used for announcing public routes.

## Site Interconnectivity

iBGP sessions are established over private Wireguard tunnels and connect all sites together, allowing for efficient routing of internal traffic.
Each site has its own set of internal CIDR blocks (see [IP Addresses](../ip-addresses)).

## Public Routes

Public routes are announced via eBGP sessions to upstream providers and are established over GRE(TAP) tunnels.
Currently, the public routes are only announced from the [Core Infrastructure](../../services/core-infrastructure) server, introducing a single point of failure.
In the future, it is planned to announce public routes from multiple sites to improve redundancy.

Public routes are announced with the ASN [201421](https://www.peeringdb.com/net/31758) using the `2001:678:dc0::/48` prefix.
