# Lab Notes
## Enterprise WAN Infrastructure Design

---

# Lab Objective

Design and implement a multi-site enterprise network that supports:

- Departmental VLAN segmentation
- Inter-VLAN routing
- Dynamic routing with OSPF
- Multi-area OSPF design
- WAN connectivity
- Internet access
- DNS resolution
- DHCP services
- NAT/PAT
- Route redistribution
- WAN redundancy

The goal was to simulate a small enterprise environment with an HQ location, a Branch location, Corporate WAN transport, and Internet connectivity.

---

# Concepts Covered

## VLAN Segmentation

The HQ and Branch locations were segmented into separate VLANs to isolate traffic and organize departments.

### HQ VLANs

| VLAN | Department |
|--------|-------------|
| 10 | IT |
| 20 | HR |
| 99 | Management |

### Branch VLANs

| VLAN | Department |
|--------|-------------|
| 30 | Sales |
| 40 | Finance |
| 50 | Guest |

---

## Layer 2 Switching

Configured access ports and trunk links between switches.

Topics reinforced:

- Access Ports
- Trunk Ports
- VLAN Membership
- Switch-to-Switch Connectivity

---

## Inter-VLAN Routing

Routers provided communication between VLANs.

Concepts reinforced:

- Default gateways
- Router interfaces
- Layer 3 forwarding
- Internal network routing

---

## OSPF Dynamic Routing

Implemented Open Shortest Path First (OSPF) throughout the environment.

Topics reinforced:

- Neighbor formation
- Link-state advertisements
- Route propagation
- SPF calculations
- Route convergence

---

## Multi-Area OSPF

The environment was divided into multiple OSPF areas.

### Area 0

Backbone WAN

### Area 1

HQ Site

### Area 2

Branch Site

Concepts reinforced:

- Area design
- Area Border Routers (ABRs)
- Backbone requirements
- Inter-area route advertisements

---

## Route Redistribution

Static routes were redistributed into OSPF.

Concepts reinforced:

- External routes
- OSPF E2 routes
- Route advertisement
- Redistribution troubleshooting

---

## WAN Design

The WAN was designed to simulate an enterprise environment.

Components:

- HQ WAN Router
- Branch WAN Router
- Corporate WAN Cloud
- ISP Router

Concepts reinforced:

- Site-to-site connectivity
- Enterprise WAN architecture
- Transit networks
- Routing domains

---

## NAT

Network Address Translation was implemented.

Concepts reinforced:

- Inside local addresses
- Inside global addresses
- NAT boundaries
- Translation tables

---

## PAT

Port Address Translation was configured using interface overload.

Concepts reinforced:

- Address conservation
- Dynamic translations
- Overload operation

---

## DHCP

Centralized DHCP services were provided from the HQ server.

Concepts reinforced:

- Automatic addressing
- DHCP scopes
- DHCP request process
- Lease assignment

---

## DNS

DNS services were hosted on the HQ server.

Concepts reinforced:

- Name resolution
- A records
- Client DNS configuration
- Enterprise DNS design

---

## Internet Connectivity

Internet access was provided through the ISP router.

Concepts reinforced:

- Default routing
- NAT/PAT operation
- Public resource access
- Internet path verification

---

## Redundancy Concepts

The Corporate WAN cloud provided a secondary enterprise transport path.

Concepts reinforced:

- Redundant paths
- Alternate route selection
- OSPF failover behavior

---

# Validation Performed

Successfully verified:

- VLAN communication
- Inter-VLAN routing
- OSPF neighbor formation
- OSPF route advertisements
- Route redistribution
- NAT translations
- PAT translations
- DHCP operation
- DNS resolution
- Internet connectivity
- WAN routing
- Corporate WAN connectivity
- End-to-end communication

---

# Major Takeaways

This lab combined concepts from multiple CCNA domains into a single enterprise topology.

The most valuable lessons learned were:

- Multi-area OSPF design
- NAT/PAT troubleshooting
- Route redistribution
- Enterprise WAN architecture
- DNS troubleshooting
- Default route propagation
- End-to-end packet flow analysis

This project required validating both forward and return traffic paths and demonstrated how routing, NAT, DNS, and WAN technologies interact in a real enterprise environment.