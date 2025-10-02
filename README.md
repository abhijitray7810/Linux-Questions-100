## 1. Linux Fundamentals (Basics) README.md
Now I'll create the comprehensive README.md files for each topic. Let me start with the first one:

# Linux Fundamentals (Basics) - README.md


# Linux Fundamentals (Basics)

## Table of Contents
- [Introduction](#introduction)
- [What is Linux?](#what-is-linux)
- [Linux Directory Structure](#linux-directory-structure)
- [Basic Navigation Commands](#basic-navigation-commands)
- [File Operations](#file-operations)
- [Text Processing](#text-processing)
- [System Information](#system-information)
- [Help and Documentation](#help-and-documentation)
- [Best Practices](#best-practices)
- [Common Pitfalls](#common-pitfalls)
- [Practice Exercises](#practice-exercises)

## Introduction

Linux is an open-source, Unix-like operating system that forms the backbone of modern computing infrastructure. From smartphones to supercomputers, web servers to cloud platforms, Linux powers the digital world. This guide covers the fundamental concepts and commands every Linux user should know.

## What is Linux?

**Linux** is:
- An **open-source** operating system kernel
- **Unix-like** in design and functionality
- **Multi-user** and **multi-tasking**
- **Portable** across different hardware platforms
- The foundation for **distributions** like Ubuntu, CentOS, Debian, Fedora

### Why Linux Matters for DevOps and Cloud:
- **Servers**: 96% of the world's top million servers run Linux
- **Cloud**: AWS, Google Cloud, Azure all Linux-based
- **Containers**: Docker and Kubernetes built on Linux
- **Development**: Preferred platform for software development
- **Cost-effective**: No licensing fees

## Linux Directory Structure

```
/ (Root)
├── bin/          # Essential user binaries
├── sbin/         # System binaries
├── etc/          # Configuration files
├── home/         # User home directories
├── root/         # Root user home
├── var/          # Variable data (logs, databases)
├── tmp/          # Temporary files
├── usr/          # User programs and data
├── opt/          # Optional software packages
├── proc/         # Process and kernel info
├── dev/          # Device files
├── boot/         # Boot loader files
├── lib/          # Shared libraries
├── media/        # Removable media
├── mnt/          # Temporary mount points
└── srv/          # Service data
```

### Key Files:
- `/etc/passwd` - User account information
- `/etc/shadow` - Encrypted user passwords
- `/etc/group` - Group information
- `/etc/hostname` - System hostname
- `/etc/hosts` - Local DNS mappings

## Basic Navigation Commands

### Print Working Directory
```bash
pwd                    # Show current directory
pwd -P                 # Show physical path (resolve symlinks)
```

### List Directory Contents
```bash
ls                     # List files
ls -l                  # Long format
ls -la                 # All files including hidden
ls -lh                 # Human-readable sizes
ls -lt                 # Sort by modification time
ls -ltr                # Reverse sort by time
ls -R                  # Recursive listing
ls --color=auto        # Colored output
```

### Change Directory
```bash
cd /path/to/directory  # Absolute path
cd ./subdirectory      # Relative path
cd ..                  # Parent directory
cd ~                   # Home directory
cd -                   # Previous directory
cd /                   # Root directory
```

## File Operations

### Create Files and Directories
```bash
touch filename.txt     # Create empty file
touch -t 202401011200 file.txt  # Set specific timestamp
mkdir directoryname    # Create directory
mkdir -p path/to/dir   # Create parent directories
mkdir -m 755 dirname   # Create with specific permissions
```

### Copy Files and Directories
```bash
cp source.txt dest.txt                    # Copy file
cp -r sourcedir/ destdir/                 # Copy directory recursively
cp -p file.txt backup.txt                 # Preserve attributes
cp -u file.txt backup.txt                 # Update only if newer
cp -v file.txt backup.txt                 # Verbose output
cp file1.txt file2.txt destination_dir/   # Multiple files
```

### Move/Rename Files
```bash
mv oldname.txt newname.txt                # Rename
mv file.txt /path/to/destination/         # Move file
mv -i file.txt newlocation/               # Interactive (prompt)
mv -u sourcedir/* destdir/                # Update only newer files
```

### Remove Files and Directories
```bash
rm filename.txt        # Remove file
rm -i filename.txt     # Interactive removal
rm -f filename.txt     # Force removal
rm -r directory/       # Remove directory recursively
rm -rf directory/      # Force recursive removal
rmdir emptydir/        # Remove empty directory
```

### View File Contents
```bash
cat file.txt           # Display entire file
cat -n file.txt        # Show line numbers
cat -b file.txt        # Number non-blank lines
less file.txt          # View file interactively
more file.txt          # Simple pager
head file.txt          # First 10 lines
head -n 20 file.txt    # First 20 lines
tail file.txt          # Last 10 lines
tail -n 50 file.txt    # Last 50 lines
tail -f file.txt       # Follow file changes
```

## Text Processing

### Search in Files
```bash
grep "pattern" file.txt                   # Search for pattern
grep -i "pattern" file.txt                # Case insensitive
grep -v "pattern" file.txt                # Invert match
grep -n "pattern" file.txt                # Show line numbers
grep -r "pattern" directory/              # Recursive search
grep -E "pattern1|pattern2" file.txt      # Extended regex
```

### Text Manipulation
```bash
sort file.txt          # Sort lines alphabetically
sort -n file.txt       # Numeric sort
sort -r file.txt       # Reverse sort
uniq file.txt          # Remove duplicate lines
uniq -c file.txt       # Count occurrences
wc file.txt            # Count lines, words, characters
wc -l file.txt         # Count lines only
cut -d: -f1 /etc/passwd  # Extract first field
paste file1.txt file2.txt  # Merge lines from files
```

## System Information

### System Details
```bash
uname -a               # All system information
uname -r               # Kernel version
uname -m               # Machine architecture
hostname               # System hostname
hostnamectl            # Detailed hostname info
uptime                 # System uptime and load
whoami                 # Current user
who am i               # Current user with details
w                      # Show logged-in users
last                   # Show login history
```

### Hardware Information
```bash
lscpu                  # CPU information
lsmem                  # Memory information
lspci                  # PCI devices
lsusb                  # USB devices
lsblk                  # Block devices
df -h                  # Disk space usage
free -h                # Memory usage
```

## Help and Documentation

### Getting Help
```bash
man command            # Manual page
man -k keyword         # Search manual pages
info command           # Info documentation
command --help         # Command help
help builtin           # Bash builtin help
type command           # Show command type
which command          # Show command location
whereis command        # Show binary, source, manual
apropos keyword        # Search manual descriptions
```

## Best Practices

### Command Line Efficiency
```bash
# Command history
history                # Show command history
!!                     # Repeat last command
!n                     # Repeat command number n
!string                # Repeat last command starting with string
Ctrl+R                 # Reverse search history

# Tab completion
Tab                    # Auto-complete commands and paths
Tab Tab                # Show all possible completions

# Navigation shortcuts
Ctrl+A                 # Move to beginning of line
Ctrl+E                 # Move to end of line
Ctrl+U                 # Clear line before cursor
Ctrl+K                 # Clear line after cursor
Ctrl+L                 # Clear screen
```

### File Management
```bash
# Always verify before destructive operations
rm -i important_file   # Interactive removal
cp -i file dest        # Interactive copy

# Use verbose mode for clarity
cp -v source dest      # Verbose copy
mv -v source dest      # Verbose move

# Create backups before modifications
cp file.txt file.txt.backup
```

## Common Pitfalls

### ❌ Common Mistakes
```bash
rm -rf /               # NEVER do this - deletes everything
rm -rf *               # Be careful with wildcards
chmod 777 file         # Too permissive - security risk
sudo chmod 000 /etc    # Can lock you out
> important_file       # Overwrites without warning
```

### ✅ Best Practices
```bash
# Use absolute paths when possible
rm -rf /home/user/temp/*    # Safer than rm -rf *

# Double-check before running
echo rm -rf /path/to/dir    # Preview command first

# Use version control for scripts
git init ~/scripts
git add script.sh
git commit -m "Initial version"
```

## Practice Exercises

### Exercise 1: Navigation
```bash
# 1. Go to your home directory
cd ~

# 2. Create a new directory called "linux-practice"
mkdir linux-practice

# 3. Navigate into it
cd linux-practice

# 4. Create subdirectories
mkdir scripts logs data

# 5. Go back to parent directory
cd ..

# 6. Remove linux-practice directory
rm -rf linux-practice
```

### Exercise 2: File Operations
```bash
# 1. Create a directory structure
mkdir -p project/{src,docs,tests}

# 2. Create files in each directory
touch project/src/main.py
touch project/docs/README.md
touch project/tests/test_main.py

# 3. List the structure
ls -R project

# 4. Copy the entire project
cp -r project project-backup

# 5. Remove original
rm -rf project
```

### Exercise 3: Text Processing
```bash
# 1. Create a sample file
cat > fruits.txt << EOF
apple
banana
apple
orange
banana
apple
EOF

# 2. Count occurrences
sort fruits.txt | uniq -c

# 3. Find lines containing 'apple'
grep "apple" fruits.txt

# 4. Remove file
rm fruits.txt
```

## Quick Reference Card

### Essential Commands
```bash
pwd, ls, cd, cat, cp, mv, rm, mkdir, touch
grep, find, man, sudo, chmod, chown
ps, top, kill, df, du, free
```

### File Permissions
```bash
r (read) = 4, w (write) = 2, x (execute) = 1
chmod 755 file    # rwxr-xr-x
chmod 644 file    # rw-r--r--
chmod 600 file    # rw-------
```

### Redirection
```bash
command > file     # Redirect output
command >> file    # Append output
command < file     # Redirect input
command 2> file    # Redirect error
command &> file    # Redirect all output
```

## Next Steps

After mastering these fundamentals, explore:
- [User & File Management](user-file-management.md)
- [Processes & System Monitoring](processes-monitoring.md)
- [Shell Scripting & Automation](shell-scripting.md)

## Resources

- **Official Documentation**: [Linux Documentation Project](https://tldp.org/)
- **Man Pages**: `man command-name`
- **Online Tutorials**: [Linux Journey](https://linuxjourney.com/)
- **Practice Environments**: [Katacoda](https://www.katacoda.com/)

---
*Remember: Mastery comes with practice. Spend time in the terminal every day!*
```

Now let me create the second README file for User & File Management:

# User & File Management README.md

```markdown
# User & File Management

## Table of Contents
- [Introduction](#introduction)
- [User Management](#user-management)
- [File Permissions](#file-permissions)
- [Ownership Management](#ownership-management)
- [Access Control Lists (ACLs)](#access-control-lists-acls)
- [Special Permissions](#special-permissions)
- [Best Practices](#best-practices)
- [Security Considerations](#security-considerations)
- [Troubleshooting](#troubleshooting)
- [Practice Exercises](#practice-exercises)

## Introduction

User and file management are fundamental aspects of Linux system administration. Proper management ensures system security, data integrity, and efficient multi-user environments. This guide covers everything from basic user creation to advanced permission management.

## User Management

### User Account Files

#### `/etc/passwd` - User Account Information
```bash
username:x:UID:GID:Comment:home_directory:shell
```

#### `/etc/shadow` - Encrypted Passwords
```bash
username:encrypted_password:last_change:min_days:max_days:warn_days:inactive:expire:reserved
```

#### `/etc/group` - Group Information
```bash
groupname:x:GID:member1,member2,member3
```

### Creating Users

#### Using `useradd` (Low-level)
```bash
# Basic user creation
sudo useradd john

# With home directory
sudo useradd -m john

# With specific home directory
sudo useradd -m -d /home/john.doe john

# With specific shell
sudo useradd -m -s /bin/bash john

# With specific UID
sudo useradd -m -u 1001 john

# With primary group
sudo useradd -m -g developers john

# With supplementary groups
sudo useradd -m -G sudo,docker,www-data john

# With comment (full name)
sudo useradd -m -c "John Smith" john

# With account expiry
sudo useradd -m -e 2024-12-31 john

# Complete example
sudo useradd -m -d /home/john -s /bin/bash -u 1001 \
             -g developers -G sudo,docker -c "John Smith" john
```

#### Using `adduser` (Interactive - Debian/Ubuntu)
```bash
sudo adduser john
# Follows interactive prompts
```

### Setting Passwords

```bash
# Set password for user
sudo passwd john

# Force user to change password at next login
sudo passwd -e john

# Lock account
sudo passwd -l john

# Unlock account
sudo passwd -u john

# Remove password
sudo passwd -d john

# Check password status
sudo passwd -S john
```

### Modifying Users

```bash
# Change user's primary group
sudo usermod -g newgroup john

# Add user to supplementary groups
sudo usermod -aG docker,nginx john

# Change home directory
sudo usermod -d /home/newhome -m john

# Change shell
sudo usermod -s /bin/zsh john

# Change UID
sudo usermod -u 2000 john

# Change username
sudo usermod -l newjohn john

# Lock account
sudo usermod -L john

# Unlock account
sudo usermod -U john

# Add comment
sudo usermod -c "John Smith - Developer" john

# Set account expiry
sudo usermod -e 2025-12-31 john
```

### Deleting Users

```bash
# Remove user (keep files)
sudo userdel john

# Remove user and home directory
sudo userdel -r john

# Remove user even if logged in
sudo userdel -f john

# Remove user and mail spool
sudo userdel -r -f john
```

### User Information Commands

```bash
# Show current user
whoami

# Show user ID and groups
id john

# Show all groups
groups john

# Show user information
finger john

# Show logged in users
who

# Show detailed user information
w

# Show last logins
last john

# Show user login history
lastlog -u john

# Show all users
getent passwd

# Show all groups
getent group
```

## File Permissions

### Understanding Permission Bits

```
Permission Types:
- r (read) = 4
- w (write) = 2  
- x (execute) = 1

Permission Groups:
- User (owner)
- Group
- Others

Example: -rw-r--r-- (644)
- User: read, write
- Group: read
- Others: read
```

### Viewing Permissions

```bash
# Long listing with permissions
ls -l filename

# Show hidden files
ls -la

# Show permissions in octal format
stat -c "%a %n" filename

# Detailed file information
stat filename

# Show file attributes
lsattr filename
```

### Changing Permissions with chmod

#### Symbolic Mode
```bash
# Add execute permission for user
chmod u+x script.sh

# Remove write permission for group
chmod g-w file.txt

# Add read permission for others
chmod o+r file.txt

# Set exact permissions
chmod u=rw,g=r,o=r file.txt

# Multiple changes
chmod u+x,g-w,o+r script.sh

# Apply to directories recursively
chmod -R 755 directory/

# Special permissions
chmod u+s executable    # Setuid
chmod g+s directory/    # Setgid
chmod +t directory/     # Sticky bit
```

#### Octal Mode
```bash
# Common permission sets
chmod 644 file.txt      # rw-r--r--
chmod 755 script.sh     # rwxr-xr-x
chmod 600 private.key   # rw-------
chmod 777 public        # rwxrwxrwx
chmod 2755 directory/   # rwxr-sr-x (setgid)
chmod 1755 /tmp         # rwxr-xr-t (sticky bit)
```

### Understanding Special Permissions

#### Setuid (4000)
```bash
chmod u+s executable    # Runs with file owner's privileges
# Example: /usr/bin/passwd
```

#### Setgid (2000)
```bash
chmod g+s directory     # New files inherit group ownership
chmod g+s executable    # Runs with file group's privileges
```

#### Sticky Bit (1000)
```bash
chmod +t /tmp           # Only file owner can delete files
# Common on /tmp directory
```

## Ownership Management

### Changing File Owner

```bash
# Change owner only
sudo chown john file.txt

# Change owner and group
sudo chown john:developers file.txt

# Change group only
sudo chown :developers file.txt

# Recursive change
sudo chown -R john:developers directory/

# Follow symbolic links
sudo chown -h john:developers symlink

# Preserve root ownership for files
sudo chown --preserve-root -R john:developers /

# Verbose output
sudo chown -v john file.txt

# Show changes
sudo chown -c john:developers file.txt

# Reference file
sudo chown --reference=ref_file target_file
```

### Changing Group Ownership

```bash
# Change group only
sudo chgrp developers file.txt

# Recursive change
sudo chgrp -R developers directory/

# Using group ID
sudo chgrp 1001 file.txt

# Verbose output
sudo chgrp -v developers file.txt
```

## Access Control Lists (ACLs)

### Installing ACL Support

```bash
# Debian/Ubuntu
sudo apt-get install acl

# RHEL/CentOS
sudo yum install acl

# Enable ACLs on filesystem
sudo tune2fs -o acl /dev/sda1
```

### Setting ACLs

```bash
# Give read access to specific user
setfacl -m u:john:r file.txt

# Give read access to specific group
setfacl -m g:developers:rw file.txt

# Set default ACL for new files in directory
setfacl -d -m u:john:rwx directory/

# Remove specific ACL
setfacl -x u:john file.txt

# Remove all ACLs
setfacl -b file.txt

# Copy ACLs from one file to another
getfacl file1.txt | setfacl -M - file2.txt
```

### Viewing ACLs

```bash
# Show ACLs
getfacl file.txt

# Show ACLs in compact form
getfacl -c file.txt

# Show default ACLs
getfacl -d directory/
```

## Special Permissions

### Understanding Special Permission Bits

```bash
# Find setuid files
find / -perm -4000 -type f 2>/dev/null

# Find setgid files
find / -perm -2000 -type f 2>/dev/null

# Find sticky bit directories
find / -perm -1000 -type d 2>/dev/null

# Find files with no owner
find / -nouser -type f 2>/dev/null

# Find files with no group
find / -nogroup -type f 2>/dev/null
```

### Advanced Permission Management

```bash
# Set immutable attribute (prevent changes)
sudo chattr +i important_file
sudo lsattr important_file

# Remove immutable attribute
sudo chattr -i important_file

# Append only attribute (logs)
sudo chattr +a logfile.log

# Compress attribute
sudo chattr +c large_file
```

## Best Practices

### User Management Best Practices

1. **Use Centralized Authentication**
```bash
# Configure LDAP/AD authentication
sudo apt-get install libnss-ldap libpam-ldap ldap-utils
```

2. **Implement Role-Based Access Control**
```bash
# Create role-based groups
sudo groupadd developers
sudo groupadd dbadmins
sudo groupadd webadmins
```

3. **Regular Account Auditing**
```bash
# Find unused accounts
sudo lastlog -b 90  # Users not logged in for 90 days

# Find accounts without passwords
sudo awk -F: '($2 == "" ) {print $1}' /etc/shadow

# Lock unused accounts
sudo usermod -L username
```

4. **Strong Password Policies**
```bash
# Install password quality checking
sudo apt-get install libpam-pwquality

# Configure password policy
sudo nano /etc/security/pwquality.conf
```

### File Permission Best Practices

1. **Principle of Least Privilege**
```bash
# Web server files
chmod 755 /var/www/html
chmod 644 /var/www/html/index.html

# Configuration files
chmod 600 /etc/application/config.conf

# Executable scripts
chmod 750 /usr/local/bin/admin_script.sh
```

2. **Regular Permission Audits**
```bash
# Find world-writable files
find / -type f -perm -002 2>/dev/null

# Find setuid/setgid files
find / -type f \( -perm -4000 -o -perm -2000 \) 2>/dev/null
```

3. **Use Groups Effectively**
```bash
# Create project group
sudo groupadd projectx
sudo usermod -aG projectx user1
sudo usermod -aG projectx user2
sudo chown -R :projectx /opt/projectx
sudo chmod -R 2775 /opt/projectx
```

## Security Considerations

### Secure User Management

```bash
# Disable root SSH login
sudo nano /etc/ssh/sshd_config
# Set: PermitRootLogin no

# Create sudo users instead
sudo usermod -aG sudo john

# Configure sudo logging
sudo nano /etc/sudoers
# Add: Defaults logfile="/var/log/sudo.log"

# Limit sudo commands
john ALL=(ALL) /usr/bin/systemctl, /usr/bin/tail
```

### File Security

```bash
# Secure sensitive files
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub
chmod 700 ~/.ssh

# Set umask for new files
echo "umask 027" >> ~/.bashrc

# Encrypt sensitive data
gpg -c sensitive_file.txt
gpg sensitive_file.txt.gpg
```

### Access Monitoring

```bash
# Monitor file access
sudo auditctl -w /etc/passwd -p wa -k passwd_changes

# Monitor user activities
sudo auditctl -w /home/ -p x -k user_executions

# View audit logs
sudo aureport -f
sudo ausearch -k passwd_changes
```

## Troubleshooting

### Common Issues and Solutions

1. **Permission Denied Errors**
```bash
# Check current permissions
ls -la file.txt

# Check ACLs
getfacl file.txt

# Verify user groups
groups username

# Check SELinux context
ls -Z file.txt
```

2. **User Login Issues**
```bash
# Check account status
sudo passwd -S username

# Check shell validity
getent passwd username

# Check home directory
ls -ld /home/username

# Check SSH configuration
sudo tail -f /var/log/auth.log
```

3. **Group Membership Problems**
```bash
# Refresh group membership
newgrp groupname

# Verify group exists
getent group groupname

# Check effective groups
id
```

## Practice Exercises

### Exercise 1: User Creation and Management
```bash
# 1. Create a new user with home directory
sudo useradd -m developer1

# 2. Set password
sudo passwd developer1

# 3. Add to supplementary groups
sudo usermod -aG docker,www-data developer1

# 4. Verify creation
id developer1
groups developer1

# 5. Test login
su - developer1

# 6. Clean up
sudo userdel -r developer1
```

### Exercise 2: Permission Management
```bash
# 1. Create test directory structure
mkdir -p ~/permission-test/{public,private,shared}

# 2. Set appropriate permissions
chmod 755 ~/permission-test/public
chmod 700 ~/permission-test/private
chmod 2775 ~/permission-test/shared

# 3. Create test files
touch ~/permission-test/public/info.txt
touch ~/permission-test/private/secret.txt
touch ~/permission-test/shared/project.txt

# 4. Set file permissions
chmod 644 ~/permission-test/public/info.txt
chmod 600 ~/permission-test/private/secret.txt
chmod 664 ~/permission-test/shared/project.txt

# 5. Verify with ls -la
ls -la ~/permission-test/
```

### Exercise 3: ACL Implementation
```bash
# 1. Create test directory
mkdir ~/acl-test
cd ~/acl-test

# 2. Create test file
echo "ACL Test File" > testfile.txt

# 3. Set ACL for specific user
setfacl -m u:john:rw testfile.txt

# 4. Set default ACL for directory
setfacl -d -m u:john:rwx .

# 5. Create new file to test default ACL
touch newfile.txt

# 6. Verify ACLs
getfacl testfile.txt
getfacl newfile.txt

# 7. Clean up
setfacl -b testfile.txt
setfacl -b newfile.txt
```

## Quick Reference

### User Management Commands
```bash
useradd, adduser     # Create users
usermod              # Modify users
userdel              # Delete users
passwd               # Manage passwords
id, groups           # Show user info
```

### Permission Commands
```bash
chmod                # Change permissions
chown                # Change owner
chgrp                # Change group
setfacl, getfacl     # Manage ACLs
umask                # Set default permissions
```

### Permission Numbers
```bash
7 = rwx (full permissions)
6 = rw- (read, write)
5 = r-x (read, execute)
4 = r-- (read only)
0 = --- (no permissions)
```

## Next Steps

Continue your Linux journey:
- [Processes & System Monitoring](processes-monitoring.md)
- [Networking & Security](networking-security.md)
- [Shell Scripting & Automation](shell-scripting.md)

## Resources

- **Documentation**: `man useradd`, `man chmod`, `man chown`
- **Books**: "Linux Bible", "UNIX and Linux System Administration Handbook"
- **Online**: Linux Documentation Project, Red Hat System Administrator's Guide
- **Practice**: Set up a home lab with virtual machines

---
*Remember: Good user and file management is the foundation of system security!*
```

Let me continue with the remaining README files. Would you like me to proceed with creating all the remaining files, or would you prefer to see them one at a time?
