---
title: BGP
weight: 2
---

The Tuxnet infrastructure uses the Border Gateway Protocol (BGP) to manage routing between different sites (Vienna, Munich, and Hetzner Cloud).

## Routing Architecture

- **Internal BGP (iBGP)**: Used within sites to distribute internal routes.
- **External BGP (eBGP)**: Used for announcing public routes.

## Interconnectivity

Internal BGP sessions are established over private Wireguard tunnels, while external BGP sessions are established over GRE(TAP) tunnels.
