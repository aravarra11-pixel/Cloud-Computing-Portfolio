# Laboratory 09 – Cloud Automation Engineer

**Course:** CCM101 – Cloud Computing  
**Laboratory Activity:** 9  
**Mission:** The Cloud Automation Engineer  
**Company:** CloudNova Technologies

## Mission Overview

In this laboratory activity, I learned how to automate repetitive tasks in a Linux environment using Bash scripting and Cron scheduling.

The mission focuses on creating an automated backup system that compresses important application data into a `.tar.gz` file. This helps reduce human error and ensures that backups can be performed regularly without manual intervention.

I used the KillerCoda Ubuntu Playground to practice Linux commands, create a Bash script, manage file permissions, and configure a scheduled backup task.

## Objectives

- Understand the fundamentals of Bash scripting.
- Create and execute a functional backup script.
- Use variables and Linux commands in automation.
- Modify file permissions using `chmod`.
- Compress directories using the `tar` command.
- Configure a Cron job to run automatically at 2:00 AM.
- Document the automation process using Markdown.
- Improve practical Linux and cloud administration skills.

## Tools and Technologies Used

- KillerCoda Ubuntu Playground
- Linux Terminal
- Bash Shell
- Nano Text Editor
- Cron Scheduler
- Git and GitHub
- Markdown

## Commands Executed

```bash
mkdir -p /root/app-data
echo "This is critical client data." > /root/app-data/data.txt
nano /root/backup.sh
chmod +x /root/backup.sh
/root/backup.sh
ls -lh /root/backups/
crontab -l
env EDITOR=nano crontab -e
```

## Backup Automation Process

1. Created an application data directory.
2. Added a sample text file to simulate important client data.
3. Created a Bash script named `backup.sh`.
4. Configured the script to generate timestamped compressed backups.
5. Granted executable permission to the script.
6. Executed and tested the backup process.
7. Configured a Cron job to run the script daily at 2:00 AM.
8. Verified the backup output and Cron configuration.

## Cron Schedule

```cron
0 2 * * * /root/backup.sh
```

This schedule runs the backup script every day at 2:00 AM according to the server's configured timezone.

## Skills Learned

Through this activity, I developed a better understanding of Linux automation, Bash scripting, file permissions, backup management, and task scheduling.

I also learned how automation can improve efficiency, consistency, and reliability in
