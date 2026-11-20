# Scenario 01: Network Connectivity Troubleshooting

## 1. Scenario Overview

**Objective:** Practise diagnosing network connectivity using Windows Command Prompt and a web browser.

The practical investigation was performed on an HP EliteBook 845 G7 running Windows 11 Pro.

## 2. Network Configuration Inspection

Executed:

```cmd
ipconfig /all
```

Recorded the following network configuration:

| Property | Result |
|---|---|
| IPv4 Address | 10.63.196.144 |
| Subnet Mask | 255.255.255.0 |
| IPv4 Default Gateway | 10.63.196.90 |
| IPv6 Default Gateway | fe80::cc30:67ff:fe29:e0f0%16 |
| DNS Server | 10.63.196.90 |

**Observation:** The computer had a valid-looking private IPv4 configuration.

## 3. Default Gateway Connectivity Test

Executed:

```cmd
ping 10.63.196.90
```

Results:

- Packets sent: 4
- Packets received: 4
- Packet loss: 0%
- Minimum latency: 5 ms
- Maximum latency: 8 ms
- Average latency: 6 ms

**Finding:** Communication with the default gateway was successful.

## 4. External IP Connectivity Test

Executed:

```cmd
ping 8.8.8.8
```

Results:

- Packets sent: 4
- Packets received: 4
- Packet loss: 0%
- Minimum latency: 133 ms
- Maximum latency: 506 ms
- Average latency: 299 ms

**Finding:** External IP connectivity was successful, although response times varied considerably.

## 5. DNS Resolution Test

Executed:

```cmd
nslookup google.com
```

Initial output indicated:

```text
DNS request timed out.
timeout was 2 seconds.
Server: Unknown
Address: 10.63.196.90
```

The lookup subsequently returned:

- IPv4 address: 142.250.187.14
- IPv6 address: 2a00:1450:4018:80e::200e

**Finding:** DNS resolution eventually succeeded after an initial timeout.

The server name appearing as Unknown did not independently establish a DNS server failure.

## 6. Browser Connectivity Verification

Opened Google Chrome and visited:

https://www.google.com

**Result:** Google loaded successfully.

This confirmed that normal web browsing was working during the investigation.

## 7. Troubleshooting Knowledge Applied

Analysed a separate simulated situation in which:

- The computer has a valid IP configuration.
- The default gateway is reachable.
- An external IP address is reachable.
- DNS lookups consistently fail.
- Websites cannot load using domain names.

**Diagnosis:** A DNS resolution problem would be the most likely cause.

Recommended investigation:

1. Verify the configured DNS server.
2. Test DNS server connectivity.
3. Investigate DNS service availability.
4. Check DNS configuration.
5. Apply an approved correction and retest.

## 8. Practical Findings

The actual computer did not have a complete internet connectivity failure.

The investigation established:

- Valid-looking IPv4 configuration.
- Successful gateway communication.
- Successful external IP communication.
- DNS resolution with an initial timeout.
- Successful browser access.

No network configuration changes were made.

## 9. Skills Practised

- Windows IP configuration inspection.
- `ipconfig /all`
- `ping`
- `nslookup`
- Default gateway troubleshooting.
- External IP connectivity testing.
- DNS troubleshooting.
- Browser connectivity verification.
- Evidence-based diagnosis.

## 10. Practical Implementation Status

**Status:** Practical investigation completed.

The exercise demonstrates how to systematically investigate network connectivity and distinguish between local network, external IP connectivity, and DNS resolution.

The investigation also demonstrated the importance of interpreting diagnostic results before making network configuration changes.
