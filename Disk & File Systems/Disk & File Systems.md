# Disk & File Systems
## Q42. How do you check disk usage in Linux?
```bash
df -h
du -sh *
```
## Q43. How do you check inode usage?
```bash
df -i
```
## Q44. Difference between ext4, xfs, and btrfs?
- ext4 → general purpose, stable.
- xfs → better for large files.
- btrfs → supports snapshots.
## Q45. How do you create a swap file?
```bash
dd if=/dev/zero of=/swapfile bs=1G count=1
chmod 600 /swapfile
mkswap /swapfile
swapon /swapfile
```
