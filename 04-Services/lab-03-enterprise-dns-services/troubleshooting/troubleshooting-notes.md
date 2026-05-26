# Troubleshooting Notes - Enterprise DNS Services

# Issue 1 - Overlapping IP Address Error

## Problem

Router-on-a-Stick subinterfaces generated overlapping network errors.

## Cause

An IP address was incorrectly assigned to the physical trunk interface.

## Resolution

Removed IP address from physical interface and assigned IP addresses only to subinterfaces.

---

# Issue 2 - DHCP Configuration Errors

## Problem

DHCP commands generated invalid input errors.

## Cause

Commands were entered in incorrect Cisco IOS configuration modes.

## Resolution

Configured DHCP settings under global configuration mode and DHCP pool mode.

---

# Issue 3 - NAT ACL Configuration Error

## Problem

ACL command failed during NAT configuration.

## Cause

ACL was entered while inside interface configuration mode.

## Resolution

Exited interface mode and configured ACL globally.

---

# Issue 4 - DNS Resolution Failure

## Problem

Initial DNS requests timed out.

## Cause

DNS service initialization delay and first-request communication establishment.

## Resolution

Verified:
- DNS service enabled
- DNS records configured
- proper DNS server assignment
- successful inter-VLAN routing

Subsequent DNS requests succeeded.

---

# Issue 5 - Command Syntax Errors

## Problem

Incorrect Cisco IOS verification commands were entered.

Example:

```text
show interface brief
```

## Resolution

Correct command used:

```text
show ip interface brief
```

---

# Final Validation

Successfully verified:

- VLAN operation
- Trunk operation
- DHCP assignment
- Inter-VLAN routing
- NAT/PAT translations
- DNS hostname resolution
- Internal HTTP access
- Simulated internet connectivity