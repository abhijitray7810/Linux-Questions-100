# File Permissions
## Q16. Explain Linux file permissions and how to read them.
- Permissions are shown as r (read), w (write), x (execute) for user, group, and others. Example: -rw-r--r-- means file with read-write for owner, read for group and others. Directory permissions include execute for traversal.
- r= (1)
- w= (2)
- x= (4)
- (-)= (0)
- (d)= Directory
- (-)= file
- drwxrwxrwx= 777 (r+w+x)= 7(1+2+4), (r+w+x)= 7(1+2+4), (r+w+x)= 7(1+2+4)
## Q17. How do you change file permissions and ownership?
```
chmod 755 filename           # Numeric mode
chmod u+x filename           # Symbolic mode
chown user:group filename    # Change ownership
chown -R user:group directory # Recursive change
```
## Q18. How do you change file permissions in Linux?
```
chmod 755 file.sh
```
## What does umask do?
- Sets default permissions for newly created files.
## Q19. What is the difference between chmod 777 and chmod 755?
- 777 gives read, write, execute to everyone (security risk). 755 gives full permissions to owner, read-execute to group and others (standard for executables).
## Q20. How to check all logged-in users?
```
who
w
```
