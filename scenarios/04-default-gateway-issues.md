# Scenario 4: Default Gateway Issues

## Problem Description
A computer can communicate with some local network devices but cannot reach destinations outside its local network.

## Symptoms
- Local devices may be accessible.
- Internet connectivity fails.
- Gateway ping may fail.

## Possible Causes
- Incorrect default gateway.
- Router malfunction.
- Network cable or Wi-Fi issue.
- Router configuration problems.
- Network firewall restrictions.

## Diagnostic Procedure

1. Run `ipconfig /all`.
2. Identify the default gateway.
3. Confirm the gateway belongs to the expected network.
4. Test gateway connectivity using `ping`.
5. Check connectivity to another local device if available.
6. Use `tracert 8.8.8.8` to investigate the route.

## Possible Resolutions
- Correct gateway settings with authorization.
- Restore network connectivity.
- Investigate router or access-point problems.
- Escalate infrastructure faults.

## Verification
- Test communication with the gateway.
- Test access to external destinations.
- Confirm normal internet access.

## Status
Documentation prepared. Practical testing pending.
