# Scenario 2: DNS Resolution Failure

## Problem Description
A user can potentially reach external IP addresses but cannot access websites using domain names.

## Symptoms
- Websites fail to load by domain name.
- Applications report name-resolution errors.
- Direct IP connectivity may still work.

## Possible Causes
- Incorrect DNS server configuration.
- DNS server unavailable.
- DNS cache problems.
- Network restrictions or firewall rules.

## Diagnostic Procedure

1. Run `ipconfig /all`.
2. Identify the configured DNS servers.
3. Run `nslookup google.com`.
4. Compare DNS results using an approved alternative DNS server if authorized.
5. Test IP connectivity separately.
6. Review recent network configuration changes.

## Possible Resolutions
- Correct DNS settings with authorization.
- Restore the approved DNS server configuration.
- Flush the DNS cache using `ipconfig /flushdns`.
- Escalate DNS server or network infrastructure issues.

## Verification
- Run `nslookup` again.
- Confirm domain names resolve correctly.
- Test access to relevant websites.

## Status
Documentation prepared. Practical testing pending.
