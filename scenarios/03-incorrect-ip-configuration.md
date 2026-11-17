# Scenario 3: Incorrect IP Configuration

## Problem Description
A computer cannot communicate correctly with other devices because its IP configuration may be incorrect.

## Symptoms
- No network connectivity.
- Invalid or unexpected IP address.
- Incorrect subnet mask or gateway.
- Duplicate IP address warnings.

## Possible Causes
- DHCP server unavailable.
- Incorrect static IP configuration.
- Duplicate IP address.
- Incorrect subnet mask.
- Network configuration changes.

## Diagnostic Procedure

1. Run `ipconfig /all`.
2. Check the IPv4 address.
3. Check the subnet mask.
4. Check the default gateway.
5. Check whether DHCP is enabled.
6. Look for an APIPA address in the `169.254.x.x` range.
7. Review any IP conflict messages.

## Possible Resolutions
- Renew the DHCP lease when appropriate.
- Correct incorrect settings with authorization.
- Resolve duplicate IP assignments.
- Escalate DHCP server issues.

## Verification
- Confirm the device has the correct IP configuration.
- Test local network communication.
- Test gateway and external connectivity.

## Status
Documentation prepared. Practical testing pending.
