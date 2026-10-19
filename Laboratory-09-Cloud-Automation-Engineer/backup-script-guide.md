
# Laboratory 09 - Backup Script Guide

## Mission Overview

This laboratory activity focuses on automating application data backups using Bash scripting and the Linux Cron scheduler. The purpose is to reduce manual work and ensure that important application files can be backed up regularly.

## 1. Creating the Application Data

The following commands were used to create a sample application directory and a test file.

```bash
mkdir app-data
echo "This is critical client data." > app-data/data.txt
```

The `mkdir` command creates the application folder, while the `echo` command creates a text file containing sample client data.

## 2. Automated Backup Script

The following Bash script was created using the nano text editor and saved as `backup.sh`.

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

## 3. Explanation of the Script

- `#!/bin/bash` specifies the Bash interpreter used to execute the script.
- `SOURCE_DIR="app-data"` identifies the directory containing the application data.
- `BACKUP_DIR="backups"` defines the directory where backup files will be stored.
- `TIMESTAMP=$(date +"%Y%m%d_%H%M%S")` generates a timestamp for the backup filename.
- `echo` displays messages in the terminal.
- `mkdir -p $BACKUP_DIR` creates the backup directory if it does not already exist.
- `tar -czf` compresses the source directory into a `.tar.gz` archive.
- The final `echo` command displays a backup completion message.

## 4. Setting File Permissions

The following command was used to make the script executable:

```bash
chmod +x backup.sh
```

The `chmod` command changes file permissions in Linux. The `+x` option adds execution permission, allowing the script to run directly as a program.

Without execution permission, running the script using `./backup.sh` may result in a Permission denied error.

## 5. Executing the Backup Script

After granting execution permission, the script was executed using:

```bash
./backup.sh
```

The script displayed the following messages:

```text
Initiating automated backup...
Backup completed successfully at [TIMESTAMP]!
```

The actual timestamp depends on when the script is executed.

## 6. Verifying the Backup

The following command was used to verify that the compressed backup file was created:

```bash
ls -l backups/
```

A successful execution produces a backup file with a name similar to:

```text
backup_20261019_140000.tar.gz
```

This filename includes the date and time when the backup was created.

## 7. Configuring the Cron Job

The following command was used to open the Linux Cron editor:

```bash
env EDITOR=nano crontab -e
```

The following cron expression was added:

```cron
0 2 * * * /root/backup.sh
```

This expression schedules the backup script to execute automatically every day at 2:00 AM according to the server's timezone.

### Explanation of Cron Fields

| Field | Value | Description |
|---|---|---|
| Minute | 0 | Executes at minute 0 |
| Hour | 2 | Executes at 2:00 AM |
| Day of Month | * | Executes every day of the month |
| Month | * | Executes every month |
| Day of Week | * | Executes every day of the week |

The five time fields determine when the command will execute.

The path `/root/backup.sh` identifies the Bash script that Cron will run.

## 8. Verifying the Cron Schedule

The following command was used to display the installed cron jobs:

```bash
crontab -l
```

The expected output is:

```cron
0 2 * * * /root/backup.sh
```

This confirms that the daily backup schedule has been installed in the crontab.

## 10. Conclusion

This activity demonstrated how Bash scripts and Cron jobs can automate repetitive tasks in Linux. By creating a backup script and configuring a daily schedule, application data can be backed up with less manual intervention.

Automation helps cloud administrators save time, reduce repetitive work, and maintain more consistent system operations.

