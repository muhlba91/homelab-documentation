---
title: Mail Services (MAIL)
weight: 4
---

The Mail Services site hosts the primary communication infrastructure. This network is internal to the cloud provider and managed as a dedicated VPC/Network.

## Network Topology

- **VPC CIDR**: `10.20.0.0/16`
- **Primary Subnet**: `10.20.0.0/24`

## Services

The mail server hosts the following components:

- **Postfix/Dovecot**: Core mail transfer and delivery.
- **Roundcube**: Web-based mail client.
- **SimpleLogin**: Mail aliasing and privacy service.
