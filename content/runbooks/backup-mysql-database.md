---
title: "Backing Up a MySQL Database"
tags: ["backup", "database", "mysql"]
author: "Runbook.site"
---

This runbook describes the process to back up a MySQL database.

## Prerequisites
- Access to the database server
- Database credentials

## Steps

1. **Login to the Database Server**
```bash
ssh user@db-server
```
2. **Dump the Database**
```bash
mysqldump -u root -p database_name > backup.sql
```
3. **Compress the Backup**
```bash
tar czf backup.tar.gz backup.sql
```
4. **Transfer the Backup to a Safe Location**
```bash
scp backup.tar.gz user@backup-server:/path/to/backup/
```
5. **Remove Old Backups**
```bash
find /path/to/backup/ -type f -mtime +30 -exec rm {} \;
```

## Verification
- Check the backup file size and integrity.
- Verify the backup exists on the backup server.