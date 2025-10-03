# User Management
## Q29. How do you create and manage users?
```bash
useradd username             # Create user
passwd username              # Set password
usermod -aG group username   # Add to group
userdel -r username          # Delete user with home
id username                  # Show user info
```

## Q30. What is sudo and how does it work?
- sudo allows permitted users to execute commands as root or another user. It provides audit trail, limited privilege escalation, and is configured in /etc/sudoers. Preferred over su for security.
