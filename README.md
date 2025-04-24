## Script: Verify_SQL_Backup_File.sql

**Description**:
This script uses the `RESTORE VERIFYONLY` command to check the **integrity** and **readability** of a SQL Server `.bak` backup file **without performing a full restore**. It's a fast and safe way to validate backups.

---

### Command:
```sql
RESTORE VERIFYONLY 
FROM DISK = 'Path\To\BackupFile.bak';
```

> 🔁 Replace `'Path\To\BackupFile.bak'` with the actual path to your `.bak` file.

---

### Use Case:
- Validate that your `.bak` file is not corrupted
- Confirm that SQL Server can read the backup format
- Include as part of an automated backup verification process

---

### What It Checks:
- Backup file structure
- Page checksums and headers
- Validity of the backup set
- Ensures the backup was taken by SQL Server and is readable

---

### Notes:
- This does **not check** whether the database can be successfully restored — it only validates the backup file’s **readability**
- To test full restorability, perform a **test restore** to a dev/test environment
- The SQL Server service account must have access to the `.bak` file path

 
