# Network Diagnostic Tools

## Overview
Windows provides several built-in tools for diagnosing network connectivity and configuration problems.

## 1. ipconfig
Displays the computer's IP configuration.

```cmd
ipconfig
```

## 2. ipconfig /all
Displays detailed network configuration, including:
- IP address
- Subnet mask
- Default gateway
- DNS servers
- DHCP status
- Physical address

```cmd
ipconfig /all
```

## 3. ping
Tests connectivity to another device or destination.

```cmd
ping 127.0.0.1
ping 192.168.1.1
ping 8.8.8.8
```

The results help investigate the local TCP/IP stack, local gateway, and external IP connectivity. A failed ping alone does not prove a device is unreachable because some systems block ICMP traffic.

## 4. nslookup
Checks DNS name resolution.

```cmd
nslookup google.com
```

## 5. tracert
Displays the network route toward a destination.

```cmd
tracert google.com
```

## 6. ipconfig /release
Releases the current DHCP-assigned IPv4 configuration.

```cmd
ipconfig /release
```

## 7. ipconfig /renew
Requests a new DHCP configuration.

```cmd
ipconfig /renew
```

## 8. ipconfig /flushdns
Clears the local DNS resolver cache.

```cmd
ipconfig /flushdns
```

## Important Considerations
- Run commands with appropriate permissions.
- Record results before making changes.
- Do not change network settings without authorization.
- Interpret diagnostic results alongside other evidence.
