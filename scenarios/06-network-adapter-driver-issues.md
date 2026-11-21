
# Scenario 06: Network Adapter Driver Issues

## 1. Scenario Overview

Network adapter drivers allow the operating system to communicate with wireless and wired network hardware.

A faulty, outdated, corrupted, or incompatible driver may cause network connectivity problems, unexpected disconnections, or complete adapter failure.

The purpose of this investigation was to inspect the wireless network adapter, verify its driver information, and check whether Windows reported any device or driver-related problems.

## 2. Troubleshooting Objectives

- Identify the installed network adapter.
- Check the adapter's operational status.
- Inspect the installed driver information.
- Verify the device status in Device Manager.
- Review driver-related events.
- Determine whether a driver problem exists.
- Recommend appropriate troubleshooting actions.

## 3. Practical Investigation

### Step 1: Identify the Network Adapter

Command:

```powershell
Get-NetAdapter
```

Findings:

| Adapter | Description | Status |
|---|---|---|
| Wi-Fi | Intel(R) Wi-Fi 6 AX200 160MHz | Up |
| Bluetooth Network Connection | Bluetooth Device (Personal Area Network) | Disconnected |

Assessment:

Windows successfully detected the Intel Wi-Fi 6 AX200 wireless adapter.

Its status was `Up`, indicating that the adapter was operational.

The Bluetooth network connection was disconnected, which was not considered a Wi-Fi adapter fault.

### Step 2: Inspect the Installed Driver

Command:

```powershell
Get-CimInstance Win32_PnPSignedDriver |
Where-Object {$_.DeviceName -like "*Intel(R) Wi-Fi 6 AX200*"} |
Select-Object DeviceName, DriverProviderName, DriverVersion, DriverDate
```

Findings:

| Property | Result |
|---|---|
| Device name | Intel(R) Wi-Fi 6 AX200 160MHz |
| Driver provider | Intel |
| Driver version | 23.120.0.3 |
| Driver date | 6 February 2025 |

Assessment:

The installed driver was provided by Intel and its version and date were successfully retrieved.

The driver date alone does not establish whether the driver is outdated or faulty.

### Step 3: Verify Device Manager Status

Procedure:

1. Open Device Manager.
2. Expand Network adapters.
3. Double-click Intel(R) Wi-Fi 6 AX200 160MHz.
4. Open the General tab.
5. Inspect the Device status section.

Finding:

Windows displayed:

`This device is working properly.`

Assessment:

Windows did not report a device-level problem with the wireless adapter.

### Step 4: Review Driver-Related Events

Procedure:

1. Open Device Manager.
2. Open the properties of Intel Wi-Fi 6 AX200.
3. Select the Events tab.
4. Review the available device events.

Finding:

No failed installation events were identified.

Assessment:

The investigation did not identify a failed driver installation.

This does not rule out every possible intermittent driver problem, but there was no evidence of an installation failure during the review.

## 4. Overall Findings

The investigation established that:

1. Windows successfully detected the Intel Wi-Fi 6 AX200 wireless adapter.
2. The adapter status was `Up`.
3. The installed driver was provided by Intel.
4. The installed driver version was 23.120.0.3.
5. Device Manager reported that the device was working properly.
6. No failed installation events were identified.

## 5. Root Cause Analysis

No network adapter driver failure was identified during the investigation.

The wireless adapter was operational, and Windows did not report a device-level error.

Although driver-related issues can cause intermittent network problems, the available evidence does not establish that the installed driver caused the packet loss observed during the previous network troubleshooting scenario.

The intermittent connectivity investigation and the driver inspection should therefore be treated as separate findings.

## 6. Resolution and Recommendations

No driver changes were necessary because no driver fault was identified.

For similar incidents, recommended troubleshooting actions include:

- Check the adapter status in Device Manager.
- Inspect the installed driver provider, version, and date.
- Review device events for installation or startup failures.
- Check for warning icons in Device Manager.
- Verify whether the adapter is enabled.
- Check the manufacturer's official website for compatible drivers when a driver problem is suspected.
- Update, roll back, or reinstall the driver only when justified by the evidence.
- Restart the computer and retest network connectivity after any necessary driver changes.

Avoid reinstalling a functioning driver without a clear reason, particularly when it is the computer's active network connection.

## 7. Skills Demonstrated

- Windows network adapter administration.
- PowerShell network diagnostics.
- Device Manager troubleshooting.
- Driver version and provider inspection.
- Device event investigation.
- Basic hardware and driver troubleshooting.
- Evidence-based technical decision-making.

## 8. Conclusion

The practical investigation confirmed that the Intel Wi-Fi 6 AX200 wireless adapter was detected and operational.

The installed driver was identified, Device Manager reported that the device was working properly, and no failed installation events were found.

No driver-related fault was established, so no driver changes were performed.

This exercise demonstrated how to investigate network adapter problems systematically without making unnecessary changes to a functioning system.
