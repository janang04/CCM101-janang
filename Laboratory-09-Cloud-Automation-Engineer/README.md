
# Laboratory 09 - Cloud Automation Engineer

## Mission Overview

This laboratory activity focused on automating application data backups using Bash scripting and the Linux Cron scheduler. A Bash script was created to compress a sample application directory into a timestamped backup file. The script was tested, given execution permission, and scheduled to run automatically every day at 2:00 AM.

## Objectives

- Understand basic Bash scripting concepts.
- Create a Bash script using the nano text editor.
- Use variables and Linux commands in a script.
- Modify script permissions using chmod.
- Execute and verify an automated backup script.
- Understand the purpose and syntax of Cron jobs.
- Configure a daily backup schedule.
- Document automation procedures using Markdown.

## Commands Executed

### Create Application Data

```bash
cd /root
mkdir app-data
echo "This is critical client data." > app-data/data.txt
cat app-data/data.txt
```

### Create the Bash Script

```bash
nano backup.sh
```

### Check and Modify Permissions

```bash
ls -l backup.sh
./backup.sh
chmod +x backup.sh
```

### Execute and Verify the Backup

```bash
./backup.sh
ls -l backups/
```

### Configure Cron

```bash
crontab -l
env EDITOR=nano crontab -e
```

Cron schedule:

```cron
0 2 * * * /root/backup.sh
```

Verify the installed schedule:

```bash
crontab -l
```

## Skills Learned

- Bash shell scripting
- Linux command-line operations
- Creating and editing scripts using nano
- Using variables and timestamps
- Managing Linux file permissions
- Compressing files using tar
- Automating backup procedures
- Configuring scheduled tasks using Cron
- Understanding Cron expressions
- Documenting technical procedures using Markdown
- Maintaining a GitHub Cloud Computing portfolio
