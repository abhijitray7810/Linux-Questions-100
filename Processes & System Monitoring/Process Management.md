# Process Management
## Q21. How do you check running processes?
```
ps aux                       # Snapshot of all processes
ps -ef | grep process_name   # Find specific process
top                          # Real-time process view
htop                         # Enhanced top (if installed)
pgrep process_name           # Find process IDs
```
## Q22. How do you kill a process?
```
kill PID                     # Terminate gracefully
kill -9 PID                  # Force kill
pkill process_name           # Kill by name
killall process_name         # Kill all processes by name
```
## Q23. What is the difference between kill and kill -9?
- kill sends SIGTERM (15) allowing graceful shutdown. kill -9 sends SIGKILL forcing immediate termination without cleanup.
## Q24. Difference between cron and at
- cron → schedules repetitive tasks.
- at → schedules one-time tasks.
## Q25. How do you check last reboot time?
```
who -b
```
