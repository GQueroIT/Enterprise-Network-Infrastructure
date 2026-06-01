# IP Addressing Scheme

## HQ Site

| VLAN | Department | Network |
|--------|-------------|------------|
| 10 | IT | 192.168.10.0/24 |
| 20 | HR | 192.168.20.0/24 |
| 99 | Management | 192.168.99.0/24 |

### HQ Services

| Device | IP Address |
|----------|-------------|
| HQ DNS/DHCP Server | 192.168.99.10 |

---

## Branch Site

| VLAN | Department | Network |
|--------|-------------|------------|
| 30 | Sales | 192.168.30.0/24 |
| 40 | Finance | 192.168.40.0/24 |
| 50 | Guest | 192.168.50.0/24 |

---

## WAN Links

| Link | Network |
|--------|------------|
| HQ WAN ↔ HQ Edge | 172.16.10.0/30 |
| Branch WAN ↔ Branch Edge | 172.16.20.0/30 |
| HQ WAN ↔ Corporate WAN | 10.1.1.4/30 |
| Branch WAN ↔ Corporate WAN | 10.1.1.8/30 |

---

## Internet Segment

| Resource | Address |
|------------|------------|
| Public DNS Server | 8.8.8.8 |