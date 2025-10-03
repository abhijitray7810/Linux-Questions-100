# Networking Basics
## Q31. How do you check network configuration?
```bash
ip addr show                 # IP addresses
ip route show                # Routing table
ss -tulpn                    # Listening ports
netstat -tulpn               # Network connections
ping hostname                # Connectivity test
```
## Q32. How to test connectivity to a server?
```bash
ping <hostname>
telnet <host> <port>
```
## Q33. What is the difference between iptables and firewalld?

- iptables → old firewall tool.
- firewalld → modern, dynamic firewall manager.

## Q34. How do you check open ports?
```bash
ss -tulpn                    # Modern replacement for netstat
lsof -i :port_number         # Check specific port
nmap localhost               # Port scan
```

## Q35. How do you check which process is using a port?
```bash
lsof -i :8080
netstat -tulnp | grep 8080
```
## Q36. Difference between SSH key authentication and password authentication?
- SSH key is more secure, uses public/private key pairs.
- Password can be brute-forced.


