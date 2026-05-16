# Linux Website Not Opening Troubleshooting Lab

## Objective
To troubleshoot and restore access to a website that is not opening on a Linux server.

---

## Scenario
The website hosted on Apache2 was not accessible through the browser.

The issue was simulated to practice Linux web server troubleshooting.

---

## Environment
- Operating System: Ubuntu Linux
- Web Server: Apache2
- Platform: VirtualBox / WSL
---

## Steps Performed

###1. Checked Apache service status
To verify whether Apache service is running:

```bash
sudo systemctl status apache2
---

### 2. Checked listening ports
To verify whether Apache is listening on port 80:

```bash
sudo ss -tulnp
---

### 3. Checked Apache configuration
To identify configuration errors:

```bash
sudo apachectl configtest
---

### 4. Verified website files
To check whether index file exists:

```bash
ls /var/www/html
---

### 5.Restarted Apache service
To restore website access:

```bash
sudo systemctl restart apache2
---

### 6. Verified website access
Opened in browser:

http://localhost

Root Cause

Apache service was stopped or website configuration was incorrect.

Resolution

Restarted Apache service and verified website files and configuration

Result

Website became accessible successfully through the browser.

Key Learning
How to troubleshoot website accessibility issues
How to check Apache service status
How to verify listening ports
How to validate Apache configuration
Basic Linux web server troubleshooting workflow  
