# Backup Script Guide
## Laboratory 09 – Cloud Automation Engineer

### 1. Backup Script Code

The following Bash script automates the process of backing up the client's application data.

```bash
#!/bin/bash

# Automated Backup Script for CloudNova Technologies

SOURCE_DIR="app-data"
BACKUP_DIR="backups"
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")

echo "Initiating automated backup..."

# Create the backup directory if it does not exist
mkdir -p $BACKUP_DIR

# Compress the source directory into a tarball (.tar.gz)
tar -czf $BACKUP_DIR/backup_$TIMESTAMP.tar.gz $SOURCE_DIR

echo "Backup completed successfully at $TIMESTAMP!"
```

### 2. File Permissions Using chmod

**Command:**

```bash
chmod +x backup.sh
```

The `chmod +x` command adds execution permission to the Bash script. This allows Linux to run `backup.sh` as a program instead of treating it as an ordinary text file.

Without execution permission, attempting to run `./backup.sh` may result in a Permission denied error.

### 3. Automated Backup Using Cron Job

**Cron expression:**

```bash
0 2 * * * /root/backup.sh
```

This command schedules the backup script to run automatically every day at exactly 2:00 AM.

### 4. Breakdown of the Five Cron Time Fields

| Field | Value | Meaning |
|---|---|---|
| Minute | `0` | Runs at minute zero. |
| Hour | `2` | Runs at 2:00 AM. |
| Day of Month | `*` | Runs every day of the month. |
| Month | `*` | Runs every month. |
| Day of Week | `*` | Runs every day of the week. |

**Full schedule:** Every day at 2:00 AM, Linux automatically executes `/root/backup.sh`.

### 5. Other Commands Used

| Command | Purpose |
|---|---|
| `mkdir app-data` | Creates the application data folder. |
| `echo "This is critical client data." > app-data/data.txt` | Creates a sample data file. |
| `nano backup.sh` | Creates and edits the Bash script. |
| `chmod +x backup.sh` | Grants execution permission. |
| `./backup.sh` | Executes the backup script. |
| `ls -l backups/` | Displays the generated backup files. |
| `tar -tzf backups/*.tar.gz` | Checks the contents of the compressed backup. |
| `crontab -e` | Opens the cron schedule editor. |
| `crontab -l` | Displays the installed cron jobs. |

### Conclusion

This activity helped me understand how Bash scripts and Cron jobs can automate repetitive server tasks. By creating a backup script, setting its execution permissions, and scheduling it with Cron, I learned how automation can save time and help protect important client data.
