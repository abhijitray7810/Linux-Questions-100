# Basic Commands
## Q39. What are essential text processing commands?
```bash
cat file.txt                 # Display file content
less file.txt                # View file interactively
head -n 10 file.txt          # First 10 lines
tail -n 10 file.txt          # Last 10 lines
tail -f file.txt             # Follow file changes
grep "pattern" file.txt      # Search text
awk '{print $1}' file.txt    # Field processing
sed 's/old/new/g' file.txt   # Stream editing
```
## Q40. How do you archive and compress files?
```bash
tar -czvf archive.tar.gz directory/  # Create compressed tar
tar -xzvf archive.tar.gz             # Extract
zip -r archive.zip directory/        # Create zip
unzip archive.zip                    # Extract zip
```
## Q41. What is cron and how do you use it?
- cron is a time-based job scheduler. Crontab format: minute hour day month weekday command. Example: 0 2 * * * /backup.sh runs daily at 2 AM.

## Q42. How do you schedule a script to run every 15 minutes?
- Add to crontab: */15 * * * * /path/to/script.sh
 ## Q43. What is the difference between > and >> redirection?
- overwrites file content, >> appends to file.
## Q44. How do you run a command in background?
- Add & at end: long_command &, or use nohup command & to persist after logout.
