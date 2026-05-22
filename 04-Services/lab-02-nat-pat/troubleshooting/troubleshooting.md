# Troubleshooting - NAT/PAT Enterprise Edge Lab

## Issue 1 - NAT Translations Not Appearing

### Symptoms

- `show ip nat translations` returned empty
- NAT statistics showed misses increasing
- External connectivity inconsistent

### Cause

NAT inside/outside interfaces were incorrectly assigned.

### Resolution

Corrected NAT roles:

```cisco
interface g0/1.10
 ip nat inside

interface g0/1.20
 ip nat inside

interface g0/0
 ip nat outside
```

---

## Issue 2 - Incorrect WAN Interface Assignment

### Symptoms

Public IP address was initially configured on the wrong interface.

### Cause

The Router-on-a-Stick trunk interface was mistakenly used as the WAN interface.

### Resolution

Moved the public IP address to:

```cisco
interface g0/0
```

---

## Issue 3 - NAT Statistics Showing Misses

### Symptoms

```cisco
Hits: 0
Misses: 30
```

### Cause

Traffic was not matching proper NAT direction.

### Resolution

Removed incorrect NAT assignments and rebuilt PAT configuration.

---

## Issue 4 - Show Commands Failing

### Symptoms

```cisco
Invalid input detected at '^' marker
```

### Cause

Show commands were executed inside global configuration mode.

### Resolution

Exited configuration mode using:

```cisco
end
```

or used:

```cisco
do show ip nat translations
```

---

## Issue 5 - Packet Tracer Interface Reinitialization

### Symptoms

NAT translations did not appear immediately after reconfiguration.

### Cause

Packet Tracer required interface reinitialization after NAT role changes.

### Resolution

Reapplied:

```cisco
no shutdown
```

to the WAN interface.

---

# Final Verification

Successful verification included:

- Inter-VLAN communication
- Successful ping to 8.8.8.8
- NAT translations displayed correctly
- PAT overload functioning properly
- Routing table verification successful