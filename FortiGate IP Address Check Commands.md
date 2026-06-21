# FortiGate IP Address Check Commands

### Check All Interface IPs


```bash
get system interface
```

### Show Detailed Interface Configuration

```bash
show system interface
```

### Check Specific Interface IP

Example for `port1`

```bash
show system interface port1
```

### Quick Interface Status

```bash
get hardware nic port1
```

### Check Routing Table (Gateway & Networks)

```bash
get router info routing-table all
```

### Check ARP Table (Connected Devices)

```bash
get system arp
```

### Check Current Public IP (using ping source test)

```bash
execute ping 8.8.8.8
```

### Check DHCP Assigned IPs

```bash
execute dhcp lease-list
```

### Linux-style Interface Summary

```bash
diagnose ip address list
```

## Example Output

```bash
port1: 192.168.1.1/24
port2: 10.0.0.1/24
wan1 : 203.x.x.x
```

## Product Reference

FortiGate Firewall by [Fortinet](https://www.fortinet.com?utm_source=chatgpt.com)
