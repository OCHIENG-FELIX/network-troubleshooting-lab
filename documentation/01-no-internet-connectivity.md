# Scenario 1: No Internet Connectivity

## Problem Description
A user reports that their computer cannot access the internet, while other devices on the same network appear to work.

## Symptoms
- Browser cannot load websites.
- Internet-dependent applications fail.
- Other devices have connectivity.

## Possible Causes
- Wi-Fi disconnected or Ethernet cable unplugged.
- Incorrect IP configuration.
- DHCP failure.
- DNS problems.
- Network adapter malfunction.

## Diagnostic Procedure

1. Check whether Wi-Fi or Ethernet is connected.
2. Confirm that airplane mode is disabled.
3. Run `ipconfig /all`.
4. Check the IP address, gateway, and DNS settings.
5. Ping the loopback address: `ping 127.0.0.1`.
6. Test the default gateway.
7. Test an external IP address such as `ping 8.8.8.8`.
8. Test DNS using `nslookup google.com`.

## Possible Resolutions
- Reconnect the network.
- Restart the network adapter where appropriate.
- Renew DHCP configuration if applicable.
- Correct authorized network settings.
- Investigate DNS configuration.
- Escalate suspected infrastructure problems.

## Verification
- Confirm the computer has a valid network configuration.
- Confirm access to the gateway.
- Test DNS resolution.
- Open websites and verify normal access.
- Confirm with the user.

## Status
Documentation prepared. Practical testing pending.
