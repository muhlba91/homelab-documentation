---
title: Main CIDR / General Use - Allocations
weight: 3
prev: munich
---

The main CIDR block for each site is used for general purpose addressing such as servers, network devices, and other infrastructure components.
These allocations are the same across all sites to maintain consistency and are lined out in this section.

| Description               | IPv4 Range                | IPv6 Range                                 |
| ------------------------- | ------------------------- | ------------------------------------------ |
| Routers                   | 10.x.0.y - 10.x.9.y       | xxx:0:1::y - xxx:0:1::y                    |
| Switches                  | 10.x.10.y - 10.x.19.y     | xxx:0:2::y - xxx:0:2::y                    |
| WiFi APs                  | 10.x.20.y - 10.x.29.y     | xxx:0:3::y - xxx:0:3::y                    |
| KVM Hosts                 | 10.x.30.y - 10.x.30.y     | xxx:0:4::y - xxx:0:4::y                    |
| Physical Servers          | 10.x.50.y - 10.x.59.y     | xxx:1000:1::y - xxx:1000:1::y              |
| Virtualised Kubernetes    | 10.x.60.y - 10.x.69.y     | xxx:1000:2::y - xxx:1000:2::y              |
| Load Balancers            | 10.x.70.y - 10.x.78.y     | xxx:1000:3::y - xxx:1000:3:9::y            |
| Kubernetes Load Balancers | 10.x.70.y - 10.x.70.y     | xxx:1000:3:10::y - xxx:1000:3:10::y        |
| Smart Home - Security     | 10.x.100.y - 10.x.109.y   | xxx:2000:1::y - xxx:2000:1::y              |
| Smart Home - Devices      | 10.x.110.y - 10.x.119.y   | xxx:2000:2::y - xxx:2000:2::y              |
| Smart Home - Entertainment| 10.x.120.y - 10.x.129.y   | xxx:2000:3::y - xxx:2000:3::y              |
| Smart Home - Office       | 10.x.130.y - 10.x.139.y   | xxx:2000:4::y - xxx:2000:4::y              |
| DHCP Range                | 10.x.150.y - 10.x.199.y   | xxx:e000::y - xxx:e000::ffff               |
