# Enterprise WAN Infrastructure & Internet Connectivity

## Project Overview

This project simulates a small enterprise environment consisting of a Headquarters (HQ) location, a Branch location, a Corporate WAN, and Internet connectivity through an ISP.

The objective was to design, build, troubleshoot, and validate a multi-site network capable of supporting internal business communications, centralized services, dynamic routing, and Internet access.

Unlike many networking labs that focus on a single technology, this project combines multiple networking concepts into a single enterprise-style deployment.

---

## Business Scenario

A growing organization requires secure communication between a Headquarters location and a remote Branch office.

The organization needs:

- Departmental network segmentation
- Dynamic routing between sites
- Centralized DNS and DHCP services
- Internet access for users at both locations
- WAN connectivity between locations
- Redundant network paths
- Scalable routing architecture

---

## Technologies Implemented

### Routing & Switching

- VLAN Segmentation
- Inter-VLAN Routing
- OSPF Dynamic Routing
- Multi-Area OSPF
- Route Redistribution
- Static Routing
- Default Routing

### Network Services

- DHCP
- DNS
- NAT
- PAT (Port Address Translation)

### WAN Technologies

- Corporate WAN Design
- Multi-Site Connectivity
- Internet Edge Connectivity
- ISP Integration

### Validation & Troubleshooting

- End-to-End Connectivity Testing
- Route Analysis
- OSPF Troubleshooting
- NAT Troubleshooting
- DNS Troubleshooting
- Return Path Validation

---

## Network Topology

![Enterprise WAN Topology](Evidence/final-topology.png)

---

## Site Architecture

### Headquarters (HQ)

#### VLAN 10 – IT

Network:

192.168.10.0/24

#### VLAN 20 – HR

Network:

192.168.20.0/24

#### VLAN 99 – Management

Network:

192.168.99.0/24

Services:

- DNS
- DHCP
- HQ Server

---

### Branch Office

#### VLAN 30 – Contractors

Network:

192.168.30.0/24

#### VLAN 40 – Finance

Network:

192.168.40.0/24

#### VLAN 50 – Guest

Network:

192.168.50.0/24

Services:

- Finance Server

---

## OSPF Design

### Area 0

Corporate WAN Backbone

### Area 1

HQ Site

### Area 2

Branch Site

This design allows efficient route advertisement and separation of routing domains while maintaining a scalable enterprise routing architecture.

---

## NAT/PAT Design

### HQ Edge Router

Provides Internet access for HQ users through PAT.

### Branch Edge Router

Provides Internet access for Branch users through PAT.

NAT boundaries were implemented at both sites to simulate real-world enterprise Internet access.

---

## Validation Performed

Successfully verified:

- VLAN communication
- Inter-VLAN routing
- OSPF neighbor formation
- OSPF route propagation
- Route redistribution
- DHCP operation
- DNS operation
- NAT translations
- PAT translations
- HQ-to-Branch communication
- Branch-to-HQ communication
- Internet connectivity
- DNS name resolution
- End-to-End packet flow

---

## Major Challenges Encountered

This project required extensive troubleshooting.

Issues resolved included:

- OSPF route propagation failures
- Missing default routes
- NAT configuration issues
- Route redistribution problems
- DNS resolution failures
- Return path routing failures
- Internet connectivity failures

Detailed troubleshooting documentation is available in:

- troubleshooting.md

---

## Key Lessons Learned

This project reinforced the importance of understanding how multiple networking technologies interact within an enterprise environment.

The most valuable lesson was learning how to troubleshoot packet flow across multiple routers and services rather than focusing on individual device configurations.

Working through routing, NAT, DNS, and WAN issues provided a much deeper understanding of enterprise networking than simply configuring each technology independently.

---

## Files Included

| File | Description |
|--------|-------------|
| README.md | Project Documentation |
| ip-addressing.md | IP Addressing Scheme |
| device-config-summary.md | Device Overview |
| lab-notes.md | Concepts and Learning Notes |
| troubleshooting.md | Troubleshooting Log |
| Evidence | Validation Screenshots |

---

## Skills Demonstrated

- Enterprise Network Design
- Routing & Switching
- WAN Technologies
- OSPF
- Route Redistribution
- DHCP
- DNS
- NAT/PAT
- Network Troubleshooting
- Infrastructure Validation