
# Automated Backup Script – Technical Guide

**Laboratory 09 – Cloud Automation Engineer**

## Introduction

This document explains the automated backup system created using Bash scripting in the KillerCoda Ubuntu Playground.

The purpose of the script is to create compressed backups of application data and prepare the backup process for automatic execution using Linux Cron.

## 1. Creating the Application Data

The following commands create a sample application directory and a text file containing dummy client data.

```bash
mkdir -p /root/app-data
echo "This is critical client data." > /root/app-data/data.txt
```

The `mkdir -p` command creates the directory if it does not already exist. The `echo` command writes sample data into `data.txt`.

## 2. Creating the Backup Script

The backup script was created using the Nano text editor.

```bash
nano /root/backup.sh
```

### Complete Bash Script

```bash
#!/bin/bash
# Automated Backup Script for CloudNova Technologies

set -e

SOURCE_DIR="/root/app-data"
BACKUP_DIR="/root/backups"
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")

echo "Initiating automated backup..."

if [ ! -d "$SOURCE_DIR" ]; then
    echo "ERROR: Source directory not found!"
    exit 1
fi

mkdir -p "$BACKUP_DIR"

tar -czf "$BACKUP_DIR/backup_$TIMESTAMP.tar.gz" \
    -C /root app-data

echo "Backup completed successfully at $TIMESTAMP!"
```

## 3. Explanation of the Script

**Shebang (`#!/bin/bash`)**

Specifies that the script should be executed using the Bash interpreter.

**Variables**

- `SOURCE_DIR` stores the location of the application data.
- `BACKUP_DIR` stores the destination of the backup files.
- `TIMESTAMP` generates a unique date and time value for the backup filename.

**Directory Validation**

The `if` statement checks whether the source directory exists before attempting to create a backup.

**mkdir -p**

Creates the backup directory if it does not already exist.

**tar -czf**

Compresses the application directory into a `.tar.gz` archive.

**set -e**

Stops the script if an unhandled command fails, helping prevent a misleading success message.

## 4. File Permissions

The following command grants executable permission to the backup script:

```bash
chmod +x /root/backup.sh
```

The `chmod` command changes file permissions, while `+x` adds permission to execute the file.

Without executable permission, attempting to run the script directly may result in a `Permission denied` error.

## 5. Executing the Backup Script

The script can be executed using:

```bash
/root/backup.sh
```

Example output:

```text
Initiating automated backup...
Backup completed successfully at 20261019_094500!
```

The timestamp depends on the actual execution time.

## 6. Verifying the Backup

To check the generated backup files:

```bash
ls -lh /root/backups/
```

To inspect the contents of the newest archive:

```bash
tar -tzf "$(ls -t /root/backups/*.tar.gz | head -n 1)"
```

Expected archive contents:

```text
app-data/
app-data/data.txt
```

## 7. Configuring the Cron Job

Cron allows Linux administrators to schedule scripts for automatic execution.

Open the Cron editor:

```bash
env EDITOR=nano crontab -e
```

Add the following schedule:

```cron
0 2 * * * /root/backup.sh
```

### Explanation of the Cron Expression

| Field | Value | Meaning |
|---|---|---|
| Minute | 0 | At minute 0 |
| Hour | 2 | At 2:00 AM |
| Day of Month | * | Every day |
| Month | * | Every month |
| Day of Week | * | Every day of the week |

The Cron expression schedules the backup script to execute every day at 2:00 AM based on the server's timezone.

## 8. Verifying the Cron Schedule

Run the following command:

```bash
crontab -l
```

Expected output:

```cron
0 2 * * * /root/backup.sh
```

This confirms that the Cron schedule has been installed. Actual automatic execution requires the Cron service and Linux environment to remain running.

## 9. Importance of Automation

Automated backups reduce the need for repetitive manual tasks and help minimize the risk of forgetting important maintenance activities.

Using Bash scripts and Cron scheduling allows cloud administrators to perform consistent operations across Linux environments.

## Conclusion

The automated backup script demonstrates how Bash scripting and Cron scheduling can simplify routine system administration tasks.

By combining executable scripts, file compression, and task scheduling, cloud engineers can improve operational efficiency and reliability.
