# Troubleshooting Log
## Enterprise WAN Infrastructure Design

---

# Overview

This project involved significantly more troubleshooting than I originally expected. While the initial goal was to build a multi-site enterprise network with WAN connectivity, DHCP, DNS, NAT/PAT, and OSPF, the majority of the learning came from identifying and resolving issues that prevented end-to-end communication.

Rather than rebuilding the network whenever a problem appeared, I focused on isolating the issue, verifying assumptions, and working through the troubleshooting process step-by-step.

---

# Issue #1 – Branch-to-HQ Communication Failure

## Symptoms

- Devices at the Branch site could not reliably communicate with resources at HQ.
- Some pings succeeded while others failed.
- OSPF appeared operational.

## Troubleshooting Steps

- Verified interface status on all routers.
- Verified OSPF neighbor relationships.
- Checked routing tables on HQ and Branch routers.
- Verified inter-VLAN routing functionality.

## Resolution

The issue was related to route propagation and incomplete route visibility between routers. OSPF neighbor relationships were operational, but not all required routes were being learned throughout the topology.

---

# Issue #2 – OSPF Route Advertisement Problems

## Symptoms

- Certain branch networks were missing from routing tables.
- Return traffic was failing.
- Some routers were learning routes while others were not.

## Troubleshooting Steps

- Reviewed OSPF neighbor relationships.
- Examined OSPF databases.
- Verified area assignments.
- Verified Area Border Router functionality.
- Reviewed route redistribution configuration.

## Resolution

OSPF advertisements were not propagating correctly throughout the topology. After reviewing OSPF configuration and route redistribution, routing tables were updated and branch networks became visible across the WAN.

---

# Issue #3 – Return Traffic Failure

## Symptoms

- Traffic successfully reached the destination.
- Reply traffic failed to return to the source.
- Packet Tracer simulation showed packets looping between routers.

## Troubleshooting Steps

- Traced packets hop-by-hop.
- Reviewed routing tables on WAN routers.
- Verified next-hop selection.
- Checked route advertisements.

## Resolution

The problem was caused by missing route information on intermediate routers. Once the correct routes were learned through OSPF, return traffic followed the proper path and communication was restored.

---

# Issue #4 – Missing Default Route on Branch WAN Router

## Symptoms

- Branch users could access internal resources.
- Internet connectivity failed.
- Packet Tracer showed traffic stopping at the Branch WAN Router.

## Troubleshooting Steps

- Examined routing tables.
- Verified WAN connectivity.
- Checked Internet path.
- Reviewed gateway of last resort configuration.

## Resolution

The Branch WAN Router did not have a default route configured.

After adding:

ip route 0.0.0.0 0.0.0.0 10.1.1.6

Internet-bound traffic successfully traversed the WAN and reached the ISP Router.

---

# Issue #5 – NAT/PAT Validation

## Symptoms

- Internet access was inconsistent during testing.
- Needed to verify whether translations were occurring.

## Troubleshooting Steps

- Reviewed NAT statistics.
- Examined translation tables.
- Generated traffic from both HQ and Branch locations.
- Verified inside and outside interfaces.

## Resolution

NAT and PAT were operating correctly. Translation tables confirmed successful address translation and Internet connectivity was restored.

---

# Issue #6 – NAT Configuration Error

## Symptoms

During troubleshooting I accidentally removed NAT inside and NAT outside interface assignments.

## Troubleshooting Steps

- Reviewed interface configurations.
- Examined NAT translations.
- Verified interface roles.

## Resolution

Reapplied NAT inside and NAT outside to the appropriate interfaces and restored PAT functionality.

---

# Issue #7 – DNS Resolution Failure

## Symptoms

- Users could communicate by IP address.
- Hostname resolution failed.

## Troubleshooting Steps

- Verified DNS records.
- Verified DHCP DNS assignments.
- Tested hostname resolution.
- Tested IP connectivity separately from DNS.

## Resolution

The issue was ultimately related to routing and communication paths rather than the DNS service itself. Once routing was corrected, hostname resolution functioned properly.

---

# Issue #8 – OSPF Route Redistribution

## Symptoms

- Some networks were visible locally but not throughout the enterprise.
- WAN routers did not learn all required networks.

## Troubleshooting Steps

- Reviewed redistribution configuration.
- Verified static route advertisements.
- Reviewed OSPF external routes.

## Resolution

Route redistribution was corrected, allowing remote networks to propagate correctly throughout the enterprise WAN.

---

# Final Validation

Successfully verified:

- VLAN segmentation
- Inter-VLAN routing
- DHCP services
- DNS services
- NAT/PAT functionality
- Multi-area OSPF
- Route redistribution
- WAN connectivity
- Internet access
- HQ-to-Branch communication
- Branch-to-HQ communication
- DNS name resolution
- End-to-end packet flow

---

# Lessons Learned

The biggest takeaway from this project was that troubleshooting is where the real learning happens.

There were multiple situations where a service appeared to be configured correctly, but communication still failed because another component in the path was broken.

This project reinforced the importance of:

- Reading routing tables carefully.
- Following packet flow from source to destination and back.
- Verifying assumptions.
- Testing one change at a time.
- Understanding how routing, NAT, DNS, and WAN technologies interact.

This was the most comprehensive networking project I have completed to date and provided hands-on experience with enterprise network design, implementation, validation, and troubleshooting.