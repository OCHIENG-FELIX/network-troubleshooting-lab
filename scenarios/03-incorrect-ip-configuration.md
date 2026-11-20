# Scenario 03: Incorrect IP Configuration

## Objective
Investigate an incorrect IP configuration by examining IPv4 settings, gateway connectivity, ARP entries, possible IP address conflicts, and DHCP lease renewal.

## Environment
- Operating System: Windows 11 Pro
- Network Adapter: Intel(R) Wi-Fi 6 AX200 160MHz
- IPv4 Address: `10.63.196.144`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `10.63.196.90`
- DHCP Server: `10.63.196.90`
- DNS Server: `10.63.196.90`
- DHCP Enabled: Yes

## Practical Investigation

### 1. Inspect IP Configuration

Command:

```cmd
ipconfig /all
```

Findings:
- The active Wi-Fi adapter had a valid private IPv4 address.
- The subnet mask was correctly configured.
- A default gateway was present.
- DHCP was enabled.
- A DHCP server and DNS server were configured.

Conclusion: No obvious IP configuration error was identified.

### 2. Test Default Gateway Connectivity

Command:

```cmd
ping 10.63.196.90
```

Results:
- Packets sent: 4
- Packets received: 4
- Packet loss: 0%
- Minimum response: 4 ms
- Maximum response: 12 ms
- Average response: 6 ms

Conclusion: The computer successfully communicated with its default gateway.

### 3. Inspect ARP Table

Command:

```cmd
arp -a
```

Findings:
- The gateway address `10.63.196.90` appeared in the ARP table.
- Its MAC address was `ce-30-67-29-e0-f0`.
- The gateway entry was dynamic.

Conclusion: The computer successfully resolved the gateway's MAC address through ARP. This did not independently establish whether the client's IP address was conflict-free.

### 4. Check for Duplicate IP Address Warnings

Tool: Windows Event Viewer.

Navigation:

`Windows Logs → System`

Findings:
- No duplicate IP address warnings were identified.
- No matching Event ID 4199 was found during the investigation.

Conclusion: No evidence of an IP address conflict was found in the inspected logs.

### 5. Test DHCP Lease Renewal

Command:

```cmd
ipconfig /renew
```

Findings:
- Windows reported disconnected media for unused Wi-Fi Direct and Bluetooth adapters.
- The active Wi-Fi adapter retained its IPv4 configuration.
- IPv4 address remained `10.63.196.144`.
- Subnet mask remained `255.255.255.0`.
- Default gateway remained `10.63.196.90`.

Conclusion: The active Wi-Fi adapter retained its network configuration after the renewal command. No obvious DHCP configuration problem was identified.

## Overall Findings

| Investigation | Result |
|---|---|
| IP configuration | Valid configuration observed |
| Gateway connectivity | Successful |
| ARP inspection | Gateway entry present |
| Duplicate IP warnings | None identified |
| DHCP renewal | Active Wi-Fi configuration retained |

## Final Conclusion

The practical investigation did not identify an incorrect IP configuration on the active Wi-Fi adapter.

The computer had a valid IPv4 address, subnet mask, default gateway, and DHCP configuration. Gateway connectivity was successful, no duplicate IP warnings were found, and the active adapter retained its configuration after DHCP renewal.

No network settings were manually changed.

## Practical Learning

This exercise demonstrated how to:

- Inspect IP configuration using `ipconfig /all`.
- Verify gateway connectivity using `ping`.
- Examine IP-to-MAC address mappings using `arp -a`.
- Investigate possible IP address conflicts through Windows Event Viewer.
- Request DHCP lease renewal using `ipconfig /renew`.
- Interpret diagnostic results and avoid changing network settings without sufficient evidence.
