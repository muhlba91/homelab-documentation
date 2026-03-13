---
title: CIDR Allocations
weight: 3
prev: peering
---

The public CIDR block `2001:678:dc0::/48` is used for announcing public routes via BGP.
This block is announced with the ASN [201421](https://www.peeringdb.com/net/31758).

## Strategy

Allocations are made with nibble boundaries, meaning that each hex digit in the address represents a specific layer of the network hierarchy.
This allows for efficient routing and management of the address space, as well as flexibility in subnetting and network design.

### Capacity Breakdown

| Level   | Prefix Length | Capacity | Bits Used              |
| ------- | ------------- | -------- | ---------------------- |
| Site    | `/56`         | 256      | 8 bits (2 hex digits)  |
| Purpose | `/60`         | 16       | 4 bits (1 hex digit)   |
| Subnet  | `/64`         | 65,536   | 4 bits (1 hex digit)   |

Total Calculation: 256 Sites \* 16 Groups \* 16 Subnets = 65,536 total /64 subnets.

The final allocations follow the pattern `2001:678:dc0:SSPG::`:

- `SS` = Site (00 to FF)
- `P` = Purpose (0 to F)
- `G` = Group (0 to F)

If VLANs are used, the last two hex digits of the subnet can be used to encode the VLAN ID, allowing for up to 256 VLANs per purpose per site.

## Allocations

### Sites

| Site                | CIDR Block               |
| ------------------- | ------------------------ |
| Core Infrastructure | `2001:678:dc0:00PG::/56` |
| VIE                 | `2001:678:dc0:01PG::/56` |
| MUC                 | `2001:678:dc0:02PG::/56` |
| BHS (OVH)           | `2001:678:dc0:03PG::/56` |

### Purposes

| Purpose           | CIDR Block               | Description                                                        |
| ----------------- | ------------------------ | ------------------------------------------------------------------ |
| Infrastructure    | `2001:678:dc0:SS00::/60` | Routers, Switches, Firewalls, IPMI, etc.                           |
| Servers           | `2001:678:dc0:SS10::/60` | Bare-metal servers, VMs, Containers, etc.                          |
| Trusted Core      | `2001:678:dc0:SS20::/60` | Secure devices that are highly trusted outside of other categories |
| Internal Services | `2001:678:dc0:SSD0::/60` | Any service reachable from the Intranet                            |
| DMZ Services      | `2001:678:dc0:SSE0::/60` | Any service reachable from the Internet                            |
| Sandbox           | `2001:678:dc0:SSF0::/60` | Sandbox and lab environments                                       |

### Subnets

This section can change frequently based on the needs of the network and the specific use cases for each site and purpose.
The subnets highlighted here are the standard allocations, but additional or different subnets may be allocated as needed.

#### Group 0: Infrastructure

| Subnet     | CIDR Block               | Description                              |
| ---------- | ------------------------ | ---------------------------------------- |
| Management | `2001:678:dc0:SS00::/64` | Network gear, like routers and switches  |

#### Group 1: Servers

| Subnet          | CIDR Block               | Description                        |
| --------------- | ------------------------ | ---------------------------------- |
| Hypervisors     | `2001:678:dc0:SS10::/64` | Proxmox and other hybervisors      |
| Kubernetes      | `2001:678:dc0:SS11::/64` | Kubernetes nodes                   |
| Containers/Pods | `2001:678:dc0:SS12::/64` | Containers/Kubernetes pod networks |

#### Group 2: Trusted Core

Currently, no allocations have been made for this category.

#### Group 3: Internal Services

Internal services may use these CIDR blocks or an internal ULA block, depending on requirements.

| Subnet          | CIDR Block               | Description                                                 |
| --------------- | ------------------------ | ----------------------------------------------------------- |
| Network         | `2001:678:dc0:SSD0::/64` | Netwok-related services                                     |
| Storage         | `2001:678:dc0:SSD1::/64` | File shares, shared storages, etc.                          |
| Ingress / Proxy | `2001:678:dc0:SSD2::/64` | Ingress controllers, reverse proxies, etc.                  |
| IoT             | `2001:678:dc0:SSD3::/64` | IoT-related services                                        |
| Applications    | `2001:678:dc0:SSDE::/64` | Any other internal application or service                   |
| Sandbox         | `2001:678:dc0:SSDF::/64` | Sandbox and lab services not hosted in the sandbox group    |

#### Group 4: DMZ Services

| Subnet          | CIDR Block               | Description                                                 |
| --------------- | ------------------------ | ----------------------------------------------------------- |
| Network         | `2001:678:dc0:SSE0::/64` | Netwok-related services                                     |
| Ingress / Proxy | `2001:678:dc0:SSE1::/64` | Ingress controllers, reverse proxies, etc.                  |
| Applications    | `2001:678:dc0:SSEE::/64` | Any other public-facing application or service              |
| Sandbox         | `2001:678:dc0:SSEF::/64` | Sandbox and lab services not hosted in the sandbox group    |

#### Group 5: Sandbox

Allocations are made randomly depending on the specific needs of the sandbox environment.
