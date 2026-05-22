# Lab Notes - NAT/PAT Enterprise Edge Lab

## Objective

The objective of this lab was to configure and troubleshoot NAT/PAT in a simulated enterprise environment using Router-on-a-Stick inter-VLAN routing and an ISP edge connection.

---

# Concepts Reinforced

## VLAN Segmentation

Two VLANs were configured:

- VLAN 10 - HR
- VLAN 20 - IT

Each VLAN used a separate subnet and default gateway.

---

## Router-on-a-Stick

Inter-VLAN routing was implemented using subinterfaces on R1.

Subinterfaces:
- G0/1.10
- G0/1.20

802.1Q encapsulation was used to transport VLAN traffic across the trunk link.

---

## NAT/PAT

PAT overload was configured to allow multiple internal devices to share a single public IP address.

Command used:

```cisco
ip nat inside source list 1 interface GigabitEthernet0/0 overload
```

---

## WAN Edge Routing

R1 connected to an ISP router using:
- 209.165.200.224/27 network

Default routing was configured to forward unknown traffic toward the ISP.

---

# Troubleshooting Lessons Learned

## NAT Direction Matters

One of the main issues encountered during the lab was incorrect NAT inside/outside assignments.

Correct configuration:
- G0/1.10 = inside
- G0/1.20 = inside
- G0/0 = outside

Incorrect NAT direction prevents translations from occurring properly.

---

## Interface State Verification

Interface operational status must always be verified during troubleshooting.

Useful command:

```cisco
show ip interface brief
```

---

## Packet Tracer NAT Behavior

Packet Tracer occasionally required interface reinitialization using:

```cisco
no shutdown
```

after NAT role changes before translations appeared correctly.

---

# Verification Commands Used

```cisco
show vlan brief
show interfaces trunk
show ip route
show ip nat statistics
show ip nat translations
show access-lists
```

---

# Final Result

- Inter-VLAN routing successful
- Internal hosts reached external server
- NAT/PAT translations verified
- ISP routing functional
- WAN edge simulation completed successfully