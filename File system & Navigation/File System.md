# 2. User & File Management
## Q10. How do you add a new user in Linux?
```bash
sudo adduser devops
```
## Q11. List basic Linux navigation and file operation commands.
```bash
ls -la                       # List all files including hidden
pwd                          # Print working directory
cd /path/to/directory        # Change directory
cp source destination        # Copy files
mv source destination        # Move/rename files
rm filename                  # Remove files
mkdir directory_name         # Create directory
rmdir directory_name         # Remove empty directory
```
## Q12. Difference between hard link and soft link?
- Hard links point directly to file's inode; if original is deleted, data remains accessible. Soft links (symlinks) point to file path; if original is deleted, link becomes broken. Hard links cannot cross filesystems, symlinks can.
- Hard link vs. soft (symbolic) link – the one-sentence difference
- Quick comparison table

| Feature | Hard link | Soft (symbolic) link |
|---|---|---|
| What is created | Another directory entry with same inode number | New inode of type “link”; stores a text pathname |
| Cross-filesystem | ❌ not allowed (inode is FS-private) | ✅ allowed (just a string) |
| Link directories | ❌ forbidden by most kernels (cycles) | ✅ allowed |
| Survives target deletion | ✅ file data kept while nlink ≥ 1 | ✅/❌ dangling “orphan” if target removed |
| Permissions | Identical to original; one set of mode bits | Own mode bits (lrwxrwxrwx); ignored for access |
| `ls -l` output | No special flag; link count > 1 | Leading “l” and “-> target” shown |
| Create command | `ln target newlink` | `ln -s target newlink` |
| Size shown by `ls` | Same as original | Length of the pathname string it stores |
| Relative paths | Works only inside same FS | Works across FS; relative to link’s location |

Visual example

```
$ echo hello > file.txt
$ ln   file.txt  hlink      # hard link
$ ln -s file.txt  slink     # soft link

$ ls -li
123456 -rw-r--r--  2 user user 6 Jun  1 09:00 file.txt
123456 -rw-r--r--  2 user user 6 Jun  1 09:00 hlink
123457 lrwxrwxrwx  1 user user 8 Jun  1 09:00 slink -> file.txt
```
## Q13. What is the difference between absolute and relative paths?
- Absolute path  
Starts at the **root of the filesystem** (`/`) and gives the complete, unambiguous route to the object.  
  -  Example: `/home/alice/docs/report.pdf`

- Relative path  
Starts at the **current working directory** (`.`) and only gives the route from there.  
  -  Example: `docs/report.pdf` (if you are already in `/home/alice`)

- Quick contrast

| Point | Absolute | Relative |
|---|---|---|
| Begins with | `/` (root) | Any character except `/` (usually `.` or dirname or `..`) |
| Value depends on CWD | ❌ never | ✅ always |
| Works from anywhere | ✅ | ❌ (breaks if CWD changes) |
| Typical use | Scripts, cron jobs, systemd units, documentation | Interactive shell, short commands inside a project |
| Parent dir shortcut | `/home/alice/../bob` still absolute | `../bob` climbs one dir from CWD |
| Shell variables that help | `pwd` always returns absolute | `$PWD` vs `..` vs `.` |
## Q14.How do you find files in Linux?
```
find /path -name "filename"  # Find by name
find /path -type f -mtime -1 # Files modified in last 24 hours
find /path -size +100M       # Files larger than 100MB
locate filename              # Quick search using updatedb database
```
## Q15. How do you check disk usage?
```
df -h                        # Disk space usage
du -sh /path/directory       # Directory size
du -ah /path | sort -rh | head -n 20  # Top 20 largest files
```

