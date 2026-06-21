## Basic FortiGate Firewall CLI Commands

### System Information

```bash
get system status
get hardware status
get system performance status

```

### Check Interface IPs

```bash
show system interface
get system interface
```

### Ping Test

```bash
execute ping 8.8.8.8
execute ping-options source <interface-ip>
```

### Traceroute

```bash
execute traceroute google.com
```

### DNS Check

```bash
get system dns
execute nslookup google.com
```

---

# Configuration Commands

## Configure Hostname

```bash
config system global
set hostname FortiGate
end
```

## Configure Interface IP

```bash
config system interface
edit port1
set ip 192.168.1.1 255.255.255.0
set allowaccess ping https ssh
next
end
```

## Configure Default Gateway

```bash
config router static
edit 1
set gateway 192.168.1.254
set device port1
next
end
```

## Configure DNS

```bash
config system dns
set primary 8.8.8.8
set secondary 1.1.1.1
end
```

---

# Firewall Policy Commands

## View Firewall Policies

```bash
show firewall policy
```

## Create Firewall Rule

```bash
config firewall policy
edit 1
set name "LAN_to_WAN"
set srcintf "port2"
set dstintf "port1"
set srcaddr "all"
set dstaddr "all"
set action accept
set schedule "always"
set service "ALL"
set nat enable
next
end
```

---

# User & Admin Commands

## Create Admin User

```bash
config system admin
edit admin2
set password password123
next
end
```

## Show Admin Users

```bash
show system admin
```

---

# Routing Commands

## Show Routing Table

```bash
get router info routing-table all
```

## Add Static Route

```bash
config router static
edit 1
set dst 0.0.0.0/0
set gateway 192.168.1.1
set device port1
next
end
```

---

# VPN Commands

## Show VPN Status

```bash
get vpn ipsec tunnel summary
diagnose vpn tunnel list
```

## Restart VPN Tunnel

```bash
diagnose vpn tunnel flush
```

---

# NAT Commands

## Enable NAT in Policy

```bash
set nat enable
```

## View Central NAT

```bash
show firewall central-snat-map
```

---

# DHCP Commands

## Configure DHCP Server

```bash
config system dhcp server
edit 1
set interface port2
set lease-time 86400
config ip-range
edit 1
set start-ip 192.168.10.10
set end-ip 192.168.10.100
next
end
next
end
```

## Check DHCP Leases

```bash
execute dhcp lease-list
```

---

# Troubleshooting Commands

## Real-Time Logs

```bash
execute log filter category 0
execute log display
```

## Log & Debug Flow

```bash
execute log display
diagnose debug reset
diagnose debug enable
diagnose debug disable
diagnose debug flow filter addr <IP>
diagnose debug flow trace start 10
diagnose debug flow trace start 100
```

## Session List

```bash
diagnose sys session list
```

## Restart Device

```bash
execute reboot
execute shutdown
```

---

# Backup & Restore

## Backup Configuration

```bash
execute backup config flash backup.conf
execute restore config flash backup.conf
```

## Show Full Configuration

```bash
show full-configuration
```
---

# HA (High Availability) Commands

## Check HA Status

```bash
get system ha status
diagnose sys ha status
```

## Force HA Failover

```bash
execute ha failover set 1
```

---

# Useful Monitoring Commands

## CPU & Memory Usage

```bash
get system performance top
```

## Connected Users

```bash
diagnose firewall auth list
```

## Active Sessions

```bash
diagnose sys session stat
```

## CLI Navigation Commands
| Command                   | Description                           |
| ------------------------- | ------------------------------------- |
| `show`                    | Displays current configuration        |
| `show full-configuration` | Displays complete configuration       |
| `get`                     | Displays runtime information          |
| `tree`                    | Shows command hierarchy               |
| `?`                       | Displays available commands           |
| `abort`                   | Cancels current configuration changes |

## Notes
- `config` → enters configuration section
- `edit` → selects object or creates new object
- `set` → changes values
- `next` → saves current object
- `end` → exits configuration mode

---

## Official Documentation

* [Fortinet Documentation Library](https://docs.fortinet.com/?utm_source=chatgpt.com)
* [FortiGate Administration Guide](https://docs.fortinet.com/product/fortigate?utm_source=chatgpt.com)

## About the Product

FortiGate Firewall by [Fortinet](https://www.fortinet.com?utm_source=chatgpt.com) is a next-generation firewall used for security, VPN, routing, web filtering, and network protection.
