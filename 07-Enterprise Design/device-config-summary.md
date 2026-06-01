# Device Configuration Summary

## HQ Site

### HQ SW1
Role:
- Core access switch
- VLAN 10 (IT)
- VLAN 20 (HR)
- VLAN 99 (Management)

Functions:
- VLAN segmentation
- Access layer connectivity

---

### HQ SW2
Role:
- Access switch

Functions:
- Additional workstation connectivity
- VLAN participation

---

### HQ SW3
Role:
- Server access switch

Functions:
- HQ server connectivity
- Trunk participation

---

### HQ Router

Role:
- Internal HQ routing

Functions:
- Inter-VLAN routing
- Default gateway services

OSPF Area:
- Area 1

---

### HQ Edge Router

Role:
- NAT/PAT boundary

Functions:
- Network Address Translation
- Port Address Translation
- Internet access for HQ users

---

### HQ WAN Router

Role:
- WAN aggregation router

Functions:
- OSPF Area Border Router (ABR)
- Route redistribution
- Corporate WAN connectivity
- Internet path selection

OSPF Area:
- Area 0
- Area 1

---

## Branch Site

### Branch WAN Router

Role:
- Branch WAN aggregation

Functions:
- OSPF Area Border Router (ABR)
- WAN connectivity
- Corporate WAN redundancy

OSPF Area:
- Area 0
- Area 2

---

### Branch Edge Router

Role:
- NAT/PAT boundary

Functions:
- Internet access
- Address translation

---

### Branch Router

Role:
- Internal branch routing

Functions:
- Inter-VLAN routing
- Default gateway services

OSPF Area:
- Area 2

---

### BSW1

Role:
- Core branch access switch

Functions:
- VLAN access
- End-user connectivity

---

### BSW2

Role:
- User access switch

Functions:
- Sales users
- Contractor users

---

### BSW3

Role:
- Finance switch

Functions:
- Finance server connectivity
- Finance workstation connectivity

---

## Services

### HQ DNS/DHCP Server

Functions:
- DNS resolution
- DHCP services

Network:
- 192.168.99.0/24

---

### Finance Server

Functions:
- Branch server resources

Network:
- VLAN 40

---

### Internet Server

Functions:
- Public Internet simulation
- DNS testing
- NAT validation

Address:
- 8.8.8.8

---

## Infrastructure

### Corporate WAN Cloud

Functions:
- MPLS / Frame Relay simulation
- Enterprise WAN transport
- Redundant path testing

---

### ISP Router

Functions:
- Internet connectivity
- Upstream routing