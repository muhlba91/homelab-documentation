---
title: Core Infrastructure (CORE)
weight: 2
---

The Core Infrastructure site serves as the central hub for the homelab's interconnectivity and central services.

## Services

| Service              | Description                                                    | URL                                            |
| -------------------- | -------------------------------------------------------------- | ---------------------------------------------- |
| **HashiCorp Vault**  | Secret management and PKI.                                     | <https://vault.platform.muehlbachler.io:8200>  |
| **VPN Gateway**      | WireGuard-based access for users and site-to-site mesh.        | <https://vpn.platform.muehlbachler.io>         |
| **BGP Router**       | Manages routing between the various sites and cloud resources. | N/A                                            |

## Configuration

### HashiCorp Vault

Vault is using a Scaleway Object Storage backend for storage and is auto-unsealed using the Google Cloud Key Management Service (KMS) integration.

Vault is automatically configured to allow authentication via GitHub and is used to manage secrets for all the other sites and services in the homelab, e.g. through the External Secrets Operator in Kubernetes.

### VPN Gateway

Currently, the VPN Gateway is solely configured to allow interconnectivity to the homelab's networks.

### BGP Router

The BGP Router manages routing between sites. It also handles the homelab's public IPv6 prefix, announcing `2001:678:dc0::/48` to the internet and routing traffic to the correct site based on destination.

For further details on the BGP configuration, see the [BGP Network](../../network/bgp) documentation.

External peers are connected via GRE(TAP) tunnels.
Internal site connectivity is achieved via WireGuard tunnels (see [VPN Gateway](#vpn-gateway)).
