# Laboratory 09 – Cloud Automation Engineer

## Mission Overview

In this laboratory, I learned how to automate backup operations using Bash scripting and Cron jobs in Ubuntu Linux. I created a sample application data folder, developed a backup script, compressed the data into a `.tar.gz` file, and configured a scheduled task to run the backup automatically every day at 2:00 AM.

## Objectives

- Understand the basic concepts of Bash scripting, variables, and Cron jobs.
- Create a sample application data folder and test file.
- Develop an automated backup script named `backup.sh`.
- Use Linux file permissions to make the script executable.
- Generate compressed backup files using the `tar` command.
- Configure a Cron job to execute the backup automatically.
- Verify the backup files and scheduled tasks.
- Document the automation process and laboratory activities.

## Commands Executed

### 1. Create Application Data

```bash
mkdir app-data
echo "This is critical client data." > app-data/data.txt
```

### 2. Create the Backup Script

```bash
nano backup.sh
```

### 3. Grant Execution Permission

```bash
chmod +x backup.sh
```

### 4. Execute the Backup Script

```bash
./backup.sh
```

### 5. Verify the Backup Files

```bash
ls -l backups/
```

### 6. Check the Backup Archive

```bash
tar -tzf backups/*.tar.gz
```

### 7. Check Existing Cron Jobs

```bash
crontab -l
```

### 8. Edit the Cron Schedule

```bash
env EDITOR=nano crontab -e
```

### 9. Scheduled Backup Command

```bash
0 2 * * * /root/backup.sh
```

### 10. Verify the Cron Schedule

```bash
crontab -l
```

## Skills Learned

- **Bash Scripting:** Learned how to write scripts that execute multiple Linux commands automatically.
- **Linux File Permissions:** Learned how to use `chmod +x` to grant execution permission to a script.
- **Variables:** Understood how variables store folder paths and timestamps for easier script management.
- **Data Backup:** Practiced creating compressed backup archives using the `tar` command.
- **Cron Scheduling:** Learned how to schedule automatic tasks using Linux Cron.
- **Linux Administration:** Improved my skills in navigating directories, creating files, and managing scripts.
- **Cloud Automation:** Understood how automation reduces repetitive manual work and improves the management of cloud servers.

## Conclusion

This laboratory gave me practical experience in automating server backup tasks using Bash and Cron. I learned that automation is useful in cloud computing because it reduces manual work, saves time, and helps ensure that important data is backed up regularly.
