---
title: "Creating a Cron Job"
tags: ["automation", "cron", "linux"]
author: "Runbook.site"
---

This runbook provides instructions on how to create a cron job on a Linux server.

## Prerequisites
- Access to the server
- Root or sudo privileges

## Steps

1. **Open Crontab**
```bash
crontab -e
```
2. **Add a Cron Job**
```bash
# m h dom mon dow command
0 2 * * * /usr/bin/backup.sh
```
3. **Save and Exit**
- Save the file and exit the editor.

4. **Verify the Cron Job**
```bash
crontab -l
```

## Verification
- Ensure the cron job is listed.
- Check logs to verify the cron job runs at the specified time.