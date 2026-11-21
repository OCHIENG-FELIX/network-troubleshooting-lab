
# Network Troubleshooting Lab

## Project Overview

This project documents common computer networking issues and demonstrates structured troubleshooting methods used in IT support environments.

It focuses on identifying network connectivity problems, investigating their possible causes, using appropriate diagnostic tools, interpreting results, and documenting findings and recommended resolutions.

The project combines networking theory with practical investigations performed on a Windows 11 computer.

## Project Objectives

- Understand fundamental networking concepts.
- Troubleshoot common network connectivity problems.
- Interpret IP addressing, subnet masks, default gateways, and DNS settings.
- Use Windows command-line networking tools.
- Investigate possible DHCP, DNS, and network adapter issues.
- Apply a systematic troubleshooting methodology.
- Analyze packet loss and network latency.
- Document findings, recommendations, and verification steps.

## Environment

- Operating System: Windows 11
- Platform: Personal computer / network troubleshooting lab
- Tools: Command Prompt, Windows PowerShell, Windows Network Settings, Device Manager
- Networking commands: `ipconfig`, `ping`, `tracert`, `nslookup`, `arp`, `route print`, `netsh`
- PowerShell commands: `Get-NetAdapter`, `Get-CimInstance`

## Project Documentation

### Documentation

- [Networking Fundamentals](documentation/networking-fundamentals.md)
- [Network Diagnostic Tools](documentation/network-diagnostic-tools.md)
- [IP Configuration Guide](documentation/ip-configuration-guide.md)

### Troubleshooting Scenarios

1. [No Internet Connectivity](scenarios/01-no-internet-connectivity.md)
2. [DNS Resolution Failure](scenarios/02-dns-resolution-failure.md)
3. [Incorrect IP Configuration](scenarios/03-incorrect-ip-configuration.md)
4. [Default Gateway Issues](scenarios/04-default-gateway-issues.md)
5. [Intermittent Network Connection](scenarios/05-intermittent-network-connection.md)
6. [Network Adapter and Driver Issues](scenarios/06-network-adapter-driver-issues.md)

### Checklists

- [Network Troubleshooting Checklist](checklists/network-troubleshooting-checklist.md)
- [Network Configuration Checklist](checklists/network-configuration-checklist.md)

## Practical Investigations and Findings

The following investigations were performed using a Windows 11 computer.

| Scenario | Practical Investigation | Finding |
|---|---|---|
| No Internet Connectivity | IP configuration, gateway connectivity, external ping, DNS resolution, browser connectivity | No complete internet outage was reproduced |
| DNS Resolution Failure | Tested configured DNS server and Google DNS using `nslookup` | Configured DNS server showed initial timeouts before successful resolution |
| Incorrect IP Configuration | Inspected DHCP settings, IP configuration, ARP table, and system events | No obvious IP configuration or duplicate-IP problem was identified |
| Default Gateway Issues | Inspected routing table, performed traceroute and gateway connectivity tests | Default gateway was reachable with no observed packet loss |
| Intermittent Network Connection | Monitored gateway and external connectivity, inspected Wi-Fi signal and hotspot usage | Packet loss and significant latency variation were observed |
| Network Adapter and Driver Issues | Inspected adapter status, driver version, Device Manager, and device events | No driver failure was identified |

These findings represent the results observed during the practical tests. They do not establish that every possible network fault was reproduced or resolved.

## Troubleshooting Methodology

Each scenario follows a structured troubleshooting process:

1. Identify the reported problem.
2. Gather information and establish the scope.
3. Inspect the network configuration.
4. Identify possible causes.
5. Perform diagnostic tests systematically.
6. Interpret the results and determine appropriate actions.
7. Verify network connectivity where applicable.
8. Document findings, limitations, and recommendations.

## Skills Demonstrated

- Network troubleshooting
- TCP/IP fundamentals
- IPv4 configuration analysis
- DNS and DHCP fundamentals
- Default gateway troubleshooting
- Routing table inspection
- Network connectivity testing
- Packet loss and latency analysis
- Wireless network diagnostics
- Windows PowerShell networking
- Network adapter and driver investigation
- Technical documentation and problem-solving

## Project Status

**Documentation completed.**

All six troubleshooting scenarios and both checklists have been prepared.

**Practical investigations completed.**

Practical testing was performed on a Windows 11 computer using Windows networking and diagnostic tools.

The investigations included IP configuration analysis, DNS testing, gateway connectivity, route tracing, packet loss monitoring, wireless signal inspection, and network adapter driver verification.

Findings, limitations, and recommendations have been documented in the respective scenario files.

## Author

**Felix Otieno Ochieng'**

- GitHub: [OCHIENG-FELIX](https://github.com/OCHIENG-FELIX)
- Portfolio: [Personal Portfolio](https://ochieng-felix.github.io/personal-portfolio/)
