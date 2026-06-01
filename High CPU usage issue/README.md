# Linux CPU Usage 100% Troubleshooting Lab

## Project Overview

This project demonstrates how to troubleshoot and resolve a high CPU usage issue in Linux.

The lab simulates a real-world scenario where a Linux server becomes slow due to CPU overutilization. The issue is intentionally created using stress-ng, then investigated using Linux monitoring and troubleshooting commands.

---

# Objective

* Simulate high CPU usage in Linux
* Monitor CPU consumption
* Identify the process causing the issue
* Resolve the issue
* Verify system recovery

---

# Lab Environment

* Ubuntu Linux

---

# Scenario

Users reported:

* Server responding slowly
* Commands taking longer than normal
* High system load

The goal was to identify the root cause and restore normal server performance.

---

# Step 1 — Update System

Update package repository before installing tools.

```bash
sudo apt update
---

# Step 2 — Install stress-ng

Install the stress testing tool.

```bash
sudo apt install stress-ng -y

Purpose:
* Used to intentionally generate high CPU load for troubleshooting practice.
---

# Step 3 — Create High CPU Usage

Run CPU stress process.

```bash
sudo stress-ng --cpu 2 --timeout 300s

Explanation:

* --cpu 2 → creates 2 CPU workers
* --timeout 300s → runs for 5 minutes

Expected Result:

* CPU usage becomes very high
* System performance slows down
---

# Step 4 — Verify CPU Usage

Open another terminal and check CPU utilization.

```bash
top

Expected Observation:

* CPU usage near 100%
* stress-ng process consuming high CPU
---

# Step 5 — Install htop (Optional)

Install advanced monitoring tool.

```bash
sudo apt install htop -y

```bash
htop

Purpose:

* Provides a user-friendly live system monitoring interface.
---

Step 6 — Check System Load

Display system load average.

```bash
uptime

Purpose:

* Shows how busy the system is.

Expected Result:

* High load average during CPU stress.
---

# Step 7 — Check CPU Information
View CPU details.

```bash
lscpu

Purpose:

* Displays CPU architecture and processor information.
---

# Step 8 — Check Running Services
View active system services.

```bash
systemctl list-units --type=service --state=running

Purpose:

* Confirms system services are functioning normally.

---

# Step 9 — Find stress-ng Process ID
Locate process ID.

```bash
ps aux | grep stress-ng

Expected Result:

* Displays PID of stress-ng process.
---

# Step 10 — Stop High CPU Process

Terminate the process.

```bash
sudo kill -9 PID

Replace:

* PID with actual process ID

Purpose:

* Stops the high CPU consumption process.
---

# Step 11 — Verify Issue Resolution

Check CPU usage again.

```bash
top


Expected Result:

* CPU usage returns to normal
* System becomes responsive

---

# Root Cause

The issue was caused by the stress-ng process intentionally consuming high CPU resources.

---

# Resolution

The high CPU process was identified using monitoring tools and terminated using the kill command.

---

# Key Learnings

* Linux CPU troubleshooting
* Monitoring processes using top and htop
* Identifying high resource consumption
* Understanding Linux process management
* Using ps and kill commands
* Basic Linux system administration

---

# Conclusion

This lab provided hands-on experience in diagnosing and resolving high CPU utilization issues in Linux systems. It improved practical troubleshooting and monitoring skills commonly required in IT Support and Linux Support roles.
