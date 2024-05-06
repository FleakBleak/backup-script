# AutoBackup - A Script for Daily File Backups

This script, `backup.sh`, automates the process of backing up files that have been modified in the last 24 hours. Given a target directory and a destination directory, it creates a compressed archive of the recent files from the target directory and moves it to the specified destination directory. This script is ideal for automating daily backups and can be easily scheduled to run at regular intervals using tools like crontab.

## How It Works

1. **Input Parameters**: The script takes two command-line arguments: the target directory where the files to be backed up are located, and the destination directory where the backup archive will be stored.

2. **File Selection**: The script checks all files in the target directory and selects those that have been modified within the last 24 hours.

3. **Backup Creation**: It creates a compressed backup archive (`.tar.gz`) containing the selected files. The backup archive is named with a timestamp to ensure uniqueness.

4. **Move to Destination**: Once the archive is created, the script moves it to the specified destination directory.

## Scheduling with Crontab

To automate daily backups, you can use crontab, a task scheduler in Unix-based systems. Here's an example of how to schedule the script to run every day at midnight:

```bash
0 0 * * * /path/to/backup.sh /path/to/target /path/to/destination
```

## Error Handling

The script includes basic error handling for common issues:

- **Incorrect Argument Count**: If the script is run with a number of arguments other than two, it displays an error message and exits.
- **Invalid Directory Paths**: If either the target or destination directory does not exist, the script shows an error message and exits.

## Conclusion

This script is a convenient tool for maintaining regular backups of files that are frequently modified. By scheduling it with crontab, you can automate daily backups without manual intervention, ensuring that your important data is always backed up and secure.
