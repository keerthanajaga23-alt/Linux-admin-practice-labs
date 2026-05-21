# Linux Disk Full Troubleshooting Lab

## Scenario

A Linux server becomes slow because disk usage is very high.
This lab simulates a real-world disk full issue and demonstrates how to troubleshoot and resolve it.

---

# 1. Check Current Disk Usage

df -h

### Explanation

This command checks available and used disk space on the system.

* df → Displays filesystem disk usage
* -h → Shows output in human-readable format (MB/GB)
Identify whether the disk is nearing full capacity.

---

# 2. Intentionally Create a Large File (Simulate Issue)

fallocate -l 2G bigfile.img

### Explanation
This command creates a 2 GB dummy file to simulate a disk space problem.

* fallocate → Quickly allocates file size
* -l 2G → Creates a 2 GB file
* bigfile.img → Name of the created file

# 3. Verify Disk Usage Increased

df -h

### Explanation

Run the disk usage command again to confirm the disk space increased after creating the large file.

---

# 4. Find Large Directories

sudo du -sh /* 2>/dev/null

### Explanation

This command checks which directories consume the most storage.

* du → Displays disk usage
* -s → Summary only
* -h → Human-readable sizes
* sudo → Access protected directories
* 2>/dev/null → Hides permission errors

---

# 5. Find Large Files

find / -type f -size +100M 2>/dev/null

### Explanation

Searches the system for files larger than 100 MB.

* find / → Search entire filesystem
* -type f → Files only
* -size +100M → Files larger than 100 MB

---

# 6. Locate the Practice File

find . -type f -size +500M

### Explanation

Searches the current directory for files larger than 500 MB.

---

# 7. Check File Size

ls -lh

### Explanation

Lists files with detailed information including file size.

* ls → List files
* -l → Long listing format
* -h → Human-readable sizes

---

# 8. Resolve the Issue (Delete File)

rm bigfile.img


### Explanation

Deletes the unnecessary large file to free disk space.

* rm → Remove file

---

# 9. Verify Disk Space Recovery

df -h

### Explanation

Checks disk usage again after cleanup.

---

# Skills Practiced

* Linux disk troubleshooting
* Storage analysis
* File system management
* Using df, du, find, and rm
* Simulating real-world Linux issues
* Basic system administration workflow
*

---
