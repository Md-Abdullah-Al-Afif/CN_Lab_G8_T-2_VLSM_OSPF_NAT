# Multi-Branch Enterprise Network: VLSM, DHCP, DNS, OSPF, VLAN and NAT-PAT

A Cisco Packet Tracer project that simulates a multi-branch enterprise network with 6 core routers, built from a single base address block using VLSM. It was created by **Md. Abdullah Al Afif** as part of a project for an academic course, and this repository exists mainly to showcase that work.

> **Privacy note:** Some information in this repository has been omitted for privacy reasons. Student IDs are not shown, and other personal details have been hidden.

---

## Academic Context

This project was completed for the Computer Networking Lab course at Southeast University, Dhaka, Bangladesh.

| Detail | Information |
|---|---|
| Course | CSE 342.19: Computer Networking Lab |
| Course code and section | CSE 342, section 19 |
| University | Southeast University, Dhaka, Bangladesh |
| Work type | Lab project (group) |
| Assessment | Lab project, demonstration, viva and final report |


## Project Overview

An enterprise connects 6 main routers (R1 to R6) in a topology. Each router serves an internal LAN with at least 3 host PCs. All addressing is derived from the base block **192.168.100.0/23** using Variable Length Subnet Masking (VLSM).

| Component | Implementation |
|---|---|
| Addressing | VLSM plan for the router links, core LANs, server subnets, VLANs and the NAT-PAT link |
| DHCP | A DHCP server in each router network gives hosts an IP address, subnet mask, default gateway and DNS server |
| DNS and Web | At least 2 DNS servers, each alongside 3 web servers hosting distinct websites |
| Routing | OSPF across all 6 core routers for full dynamic reachability |
| Switching | 2 switches forming 3 VLANs, with access ports and trunk links |
| Border | NAT-PAT on 2 edge routers to translate private addresses into public ones |

## Network Requirements

| Network | Requirement |
|---|---|
| R1 LAN | 35 hosts |
| R2 LAN | 25 hosts |
| R3 LAN | 16 hosts |
| R4 LAN | 12 hosts |
| R5 LAN | 8 hosts |
| R6 LAN | 4 hosts |
| Router-to-router links | 4 addresses per link (6 links) |
| VLAN 101 | 30 hosts |
| VLAN 102 | 15 hosts |
| VLAN 103 | 10 hosts |
| NAT router LAN | 15 hosts |

Each host count is the minimum number of usable host addresses the subnet must provide, with the default gateway included. Server subnets (DHCP, DNS and web servers) are sized as part of the VLSM plan.

## Repository Contents

| Item | Format | Description |
|---|---|---|
| `README.md` | Markdown | This file |
| Question | PDF | The project question with all network parameters |
| Report | PDF | The solution: VLSM plan with the IP addressing table, configuration details and discussion |
| Packet Tracer file | `.pkt` | The complete network simulation |

## Opening the Simulation

1. Install **Cisco Packet Tracer**.
2. Download the `.pkt` file from this repository.
3. Open it in Packet Tracer and wait for the links to turn green.
4. Run the checks below from the host PCs and routers.

A `.pkt` file is binary, so GitHub cannot preview it and it must be downloaded first. Use the same or a newer Packet Tracer version than the one that created the file, because older versions often cannot open files saved in newer ones.

## How Each Part Is Verified

| Task | Check |
|---|---|
| VLSM plan | Interface addresses on routers and hosts match the IP addressing table in the report |
| DHCP | Host PCs set to DHCP receive an address, subnet mask, default gateway and DNS server |
| DNS and Web | Each website opens by domain name in the browser of a host PC |
| OSPF | `show ip route` and `show ip ospf neighbor` on the routers; successful pings between different router LANs |
| VLAN | A ping between devices in the same VLAN succeeds; a ping across different VLANs fails |
| NAT-PAT | `show ip nat translations` on the edge router and packet simulation mode |

## Tools

- Cisco Packet Tracer

## Copyright and Usage

Copyright (c) 2026 Md. Abdullah Al Afif. All rights reserved.

This repository is published to showcase my academic work. No open-source license is applied, so the following terms describe what is and is not permitted.

**Permitted**

- Viewing, downloading and studying the work for personal learning and educational purposes.

**Conditions**

- Anyone who uses or refers to this work must give proper credit by naming the author, **Md. Abdullah Al Afif**, and linking to this repository.

Example reference:

> Md. Abdullah Al Afif. *Multi-Branch Enterprise Network: VLSM, DHCP, DNS, OSPF, VLAN and NAT-PAT*. Computer Networking Lab project, CSE 342.19, Southeast University, Dhaka, Bangladesh. Available on GitHub.

**Not permitted without my written permission**

- Commercial use, including selling the work or using it in a paid product or service.
- Republishing, redistributing or presenting the work as your own.
- Submitting the work, or a copy or adaptation of it, as your own coursework. This is plagiarism.

**Scope**

These terms cover the original work in this repository, which is the report and the Packet Tracer simulation. The project question is based on material provided by the course and is included for context only.
