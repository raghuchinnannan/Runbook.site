---
title: "Restoring a MySQL Database"
tags: ["restore", "database", "mysql"]
author: "Runbook.site"
---

This runbook details the steps to restore a MySQL database from a backup.

## Prerequisites
- Access to the database server
- Database credentials
- Backup file available

## Steps

1. **Login to the Database Server**
```bash
ssh user@db-server
```
2. **Transfer the Backup File**
```bash
scp user@backup-server:/path/to/backup/backup.tar.gz .
```
3. **Extract the Backup**
```bash
tar xzf backup.tar.gz
```
4. **Restore the Database**
```bash
mysql -u root -p database_name < backup.sql
```
5. **Verify the Restoration**
```bash
mysql -u root -p -e "SHOW TABLES;" database_name
```

## Verification
- Check that all tables and data are present in the database.
- Verify the application functionality that depends on the database.