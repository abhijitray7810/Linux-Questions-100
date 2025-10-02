# System Information
## Q27. How do you check system resources?
```
free -h                      # Memory usage
cat /proc/cpuinfo            # CPU information
lscpu                        # CPU architecture
uptime                       # System load
vmstat 1 5                   # Virtual memory statistics
```
## Q28. How do you check system logs?
```
journalctl                   # Systemd logs
journalctl -u service_name   # Service-specific logs
tail -f /var/log/syslog      # Real-time log viewing
dmesg                        # Kernel ring buffer
```
