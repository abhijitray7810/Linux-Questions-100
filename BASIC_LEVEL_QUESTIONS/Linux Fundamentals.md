# 1. Linux Fundamentals (Basics)

## Q1. What is Linux, and how is it different from Unix?
- Linux is an open-source operating system based on Unix.
- Differences: Linux is free & open-source, Unix is proprietary; Linux supports more hardware platforms.
## Q2. why is it important for DevOps?
- DevOps engineers rely on Linux for running web/app servers, automating deployments, managing cloud infrastructure, and handling system monitoring. It's the backbone of most cloud platforms and containerization technologies.
## Q3. What are the main components of Linux OS?
- Kernel
- System libraries
- System utilities
- Hardware layer
## Q4. How do you check Linux version and kernel version?
```bash
cat /etc/os-release
uname -r
```
## Q5. How do you check the Linux version and distribution details?
```bash
cat /etc/os-release          # Shows OS version and distribution
uname -r                     # Shows kernel version
lsb_release -a               # Shows distribution-specific information
hostnamectl                  # Shows system information including OS
```
## Q6. Explain the Linux directory structure and key directories.
- / - Root directory
- /bin - Essential user binaries
- /sbin - System binaries
- /etc - Configuration files
- /home - User home directories
- /var - Variable data (logs, databases)
- /tmp - Temporary files
- /usr - User programs and data
- /opt - Optional software packages
- /proc - Process and kernel information
- /dev - Device files
## Q7. What is the difference between su and sudo?
- su → switch user (needs root password).
- sudo → run commands as root (needs user in sudoers).
## Q8. What is the root user and what are its privileges?
- The root user (superuser) has unlimited privileges including accessing any file/directory, installing/removing software, modifying system configurations, managing users/groups, starting/stopping services, and binding to privileged ports (<1024).
## Q9. How do you check system uptime?
```bash
uptime
```
