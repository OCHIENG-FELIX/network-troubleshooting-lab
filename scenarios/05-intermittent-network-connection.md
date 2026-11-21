
# Scenario 05: Intermittent Network Connection

## 1. Scenario Overview

A user reports that their internet connection occasionally becomes slow or unstable, even though the computer remains connected to Wi-Fi.

Intermittent connectivity can result from wireless interference, weak signal strength, hotspot instability, network congestion, or other network-related problems.

The purpose of this investigation was to monitor the wireless connection, identify packet loss, measure latency, and assess possible causes of network instability.

## 2. Troubleshooting Objectives

- Inspect the wireless network connection.
- Check Wi-Fi signal strength and connection details.
- Monitor communication with the default gateway.
- Test connectivity to an external IP address.
- Identify packet loss and latency variations.
- Investigate possible sources of network instability.

## 3. Practical Investigation

### Step 1: Inspect the Wireless Connection

Command:

```cmd
netsh wlan show interfaces
```

Initial findings:

- Connection state: Connected
- SSID: OPPO A17k
- Radio type: 802.11n
- Channel: 1
- Receive rate: 72.2 Mbps
- Transmit rate: 72.2 Mbps

Assessment:

The computer was successfully connected to the OPPO A17k mobile hotspot using an 802.11n wireless connection.

### Step 2: Inspect IP Configuration

Command:

```cmd
ipconfig
```

Findings:

- IPv4 address: `10.63.196.144`
- Default gateway: `10.63.196.90`

Assessment:

The computer had an IPv4 address and a configured default gateway.

### Step 3: Monitor Gateway Connectivity

Command:

```cmd
ping -t 10.63.196.90
```

The continuous ping test was allowed to run before being stopped using `Ctrl + C`.

Results:

- Packets sent: 27
- Packets received: 26
- Packets lost: 1
- Packet loss: 3%
- Minimum latency: 2 ms
- Maximum latency: 147 ms
- Average latency: 21 ms

Assessment:

One packet was lost during the test. The gateway also showed some latency variation.

This provided an initial indication of possible intermittent connectivity.

### Step 4: Test External Connectivity

Command:

```cmd
ping -n 30 8.8.8.8
```

Results:

- Packets sent: 30
- Packets received: 29
- Packets lost: 1
- Packet loss: 3%
- Minimum latency: 35 ms
- Maximum latency: 325 ms
- Average latency: 95 ms

Assessment:

The external destination was reachable, but one packet was lost. Response times varied considerably.

### Step 5: Inspect Wi-Fi Signal Strength

Command:

```cmd
netsh wlan show interfaces
```

Finding:

- Signal strength: 90%

Assessment:

The wireless signal was strong. Weak signal strength was therefore unlikely to be the main explanation for the observed packet loss.

However, a strong signal does not eliminate wireless interference, congestion, or hotspot instability.

### Step 6: Perform a Longer Gateway Connectivity Test

Command:

```cmd
ping -n 50 10.63.196.90
```

Results:

- Packets sent: 50
- Packets received: 49
- Packets lost: 1
- Packet loss: 2%
- Minimum latency: 2 ms
- Maximum latency: 467 ms
- Average latency: 30 ms

Assessment:

The longer test again recorded packet loss and considerable latency variation.

The repeated results strengthened the evidence that intermittent network instability was occurring during the investigation.

### Step 7: Recheck Wireless Connection Details

Command:

```cmd
netsh wlan show interfaces
```

Latest findings:

- Channel: 1
- Radio type: 802.11n
- Receive rate: 65 Mbps
- Transmit rate: 65 Mbps
- Signal strength: 90%

Comparison:

| Measurement | Initial | Latest |
|---|---:|---:|
| Channel | 1 | 1 |
| Radio type | 802.11n | 802.11n |
| Receive rate | 72.2 Mbps | 65 Mbps |
| Transmit rate | 72.2 Mbps | 65 Mbps |
| Signal strength | 90% | 90% |

Assessment:

The signal strength remained strong, although the negotiated wireless link rate decreased slightly.

Wireless link rates can fluctuate with changing radio conditions and network activity. This change alone does not establish a fault.

## 4. Additional Investigation: Hotspot Usage

During the investigation, it was established that other devices were actively using the OPPO A17k hotspot.

Assessment:

Multiple connected devices may contribute to network congestion and increased latency, depending on their network activity and the hotspot's available capacity.

Hotspot congestion is a possible contributing factor, but it has not been confirmed as the cause of the observed packet loss.

## 5. Overall Findings

The investigation established that:

1. The computer remained connected to the mobile hotspot.
2. The wireless signal strength was consistently 90%.
3. Gateway testing recorded packet loss of 3% and later 2%.
4. External connectivity testing recorded 3% packet loss.
5. Gateway latency reached 467 ms during the longer test.
6. External latency reached 325 ms.
7. The negotiated wireless link rate changed from 72.2 Mbps to 65 Mbps.
8. Other devices were actively using the hotspot.

## 6. Root Cause Analysis

Intermittent packet loss and latency variation were observed during testing.

Weak Wi-Fi signal strength was unlikely to be the main cause because the signal remained at 90%.

Possible contributing factors include:

- Mobile hotspot congestion.
- Wireless interference.
- Temporary hotspot instability.
- Network congestion beyond the local wireless connection.

The exact root cause could not be confirmed from the available evidence.

## 7. Recommended Next Steps

To investigate further:

1. Temporarily disconnect other devices from the hotspot.
2. Repeat the gateway test using `ping -n 50 10.63.196.90`.
3. Repeat the external connectivity test using `ping -n 50 8.8.8.8`.
4. Compare packet loss and response times with the earlier results.
5. If packet loss persists, investigate wireless interference and hotspot stability.
6. If gateway communication is stable but external connectivity remains poor, investigate the mobile network or upstream connection.

No network configuration changes were made during this investigation.

## 8. Skills Demonstrated

- Wireless network diagnostics.
- IP configuration inspection.
- Continuous ping monitoring.
- Packet loss analysis.
- Network latency interpretation.
- Wireless signal assessment.
- Basic hotspot troubleshooting.
- Evidence-based root cause investigation.

## 9. Conclusion

The practical investigation identified intermittent packet loss and significant latency variation while connected to an OPPO A17k mobile hotspot.

Although the Wi-Fi signal remained strong, the network experienced occasional packet loss during both local gateway and external connectivity tests.

Other devices were actively using the hotspot, making network congestion a possible contributing factor.

The exact cause remains unconfirmed. Further testing under reduced hotspot load is recommended to establish whether congestion contributes to the instability.
