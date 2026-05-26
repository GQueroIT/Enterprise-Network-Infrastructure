# Lab Notes - Enterprise DNS Services

## Primary Focus

This lab focused on integrating multiple networking services into a segmented enterprise-style environment.

---

# Core Technologies Used

- VLANs
- Trunking
- Router-on-a-Stick
- DHCP
- DNS
- NAT/PAT
- HTTP Services

---

# Important Concepts Reinforced

## Router-on-a-Stick

The physical router interface does not receive an IP address.

Subinterfaces are used to route traffic between VLANs using 802.1Q encapsulation.

Example:

```text
g0/1.10
g0/1.20
g0/1.99
```

---

# NAT/PAT

PAT allowed multiple internal hosts to share a single public IP address.

The following concepts were reinforced:

- ip nat inside
- ip nat outside
- access-lists for translation matching
- overload keyword usage

---

# DNS

DNS allowed internal hostname resolution for:

www.smartech.local

DNS troubleshooting reinforced the importance of:
- service status
- DNS records
- client DNS assignment
- application-layer troubleshooting

---

# Key Takeaway

This lab demonstrated how enterprise infrastructure services depend on each other to function properly.

A failure at:
- Layer 2
- Layer 3
- DHCP
- DNS
- NAT

could impact overall network functionality.