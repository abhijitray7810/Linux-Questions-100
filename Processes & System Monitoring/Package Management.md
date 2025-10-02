# Package Management
## Q19. How do you install software in different Linux distributions?
```
# Debian/Ubuntu
apt update && apt install package
apt-get install package

# RHEL/CentOS
yum install package
dnf install package

# Universal
snap install package
flatpak install package
```
## Q20. How do you check installed packages?
```
dpkg -l                      # Debian/Ubuntu
rpm -qa                      # RHEL/CentOS
yum list installed           # RHEL/CentOS
apt list --installed         # Debian/Ubuntu
```
