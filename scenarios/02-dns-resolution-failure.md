## Practical Investigation Results

### Objective
Investigate repeated DNS request timeouts when using the configured DNS server.

### Environment
- Client IPv4 address: `10.63.196.144`
- Configured DNS server: `10.63.196.90`
- Default gateway: `10.63.196.90`
- Comparison DNS server: `8.8.8.8`

### Tests Performed

**1. DNS server connectivity**

Command:
```cmd
ping 10.63.196.90
```

Result:
- Packets sent: 4
- Packets received: 4
- Packet loss: 0%
- Average response time: 5 ms

Conclusion: The configured DNS server was reachable at the IP level.

**2. Configured DNS server – Microsoft**

Command:
```cmd
nslookup microsoft.com 10.63.196.90
```

Result: Initial DNS request timeout after 2 seconds, followed by successful resolution.

**3. Configured DNS server – Google**

Command:
```cmd
nslookup google.com 10.63.196.90
```

Result: Initial DNS request timeout after 2 seconds, followed by successful resolution.

**4. Public DNS comparison – Microsoft**

Command:
```cmd
nslookup microsoft.com 8.8.8.8
```

Result: Successful resolution without an observed timeout.

**5. Public DNS comparison – Google**

Command:
```cmd
nslookup google.com 8.8.8.8
```

Result: Successful resolution without an observed timeout.

### Findings

- The configured DNS server was reachable.
- Both tested domains eventually resolved through the configured DNS server.
- Both domains resolved through Google Public DNS without the observed initial timeout.
- The repeated delays suggest a possible issue with the configured DNS server or its upstream forwarding service.

### Conclusion

No persistent DNS resolution failure was established. However, repeated initial timeouts were observed when querying the configured DNS server.

Further investigation by a network administrator would be required to identify the underlying cause. No DNS settings were changed during testing.

### Practical Learning

This exercise demonstrated how to:
- Test DNS server connectivity using `ping`.
- Query DNS servers directly using `nslookup`.
- Compare configured DNS with a public DNS resolver.
- Distinguish DNS response delays from complete DNS resolution failure.
- Record findings and identify appropriate escalation procedures.
