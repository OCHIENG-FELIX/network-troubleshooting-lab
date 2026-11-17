# IP Configuration Guide

## Overview
IP configuration enables a device to communicate with other devices on a network.

## Main Configuration Components

| Component | Purpose |
|---|---|
| IP Address | Identifies the device |
| Subnet Mask | Defines the network portion |
| Default Gateway | Provides access to other networks |
| DNS Server | Resolves domain names |
| DHCP | Automatically assigns network settings |

## Example Configuration

- IP Address: `192.168.1.20`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `192.168.1.1`
- DNS Server: `192.168.1.1`

These are illustrative private-network values, not settings to copy blindly.

## DHCP Configuration
DHCP automatically provides network configuration to clients.

A device may fail to obtain a valid IPv4 configuration if the DHCP server is unavailable or communication is interrupted.

An address beginning with `169.254` often indicates that Windows has assigned itself an APIPA address because it did not obtain an IPv4 address from DHCP.

## Static IP Configuration
A static IP address is manually configured.

Before assigning one:
- Confirm the correct network range.
- Check that the address is not already in use.
- Confirm the subnet mask and gateway.
- Obtain authorization from the network administrator.

## Verification
Use:

```cmd
ipconfig /all
```

Then test connectivity using appropriate ping and DNS commands.
