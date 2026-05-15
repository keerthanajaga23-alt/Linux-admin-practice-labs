# Linux Server Down Troubleshooting Lab

## Objective
To troubleshoot and restore a Linux web server when it is down.

---

## Scenario
Apache2 web server was not accessible. The service was intentionally stopped to simulate a real server outage.

Users were unable to open the website in the browser.

---

## Environment
- Ubuntu Linux
- Apache2 Web Server
- VirtualBox / WSL

---

## Steps performed

###1. Checked service status

To verify whether Apache service is running or stopped:
```bash
sudo systemctl status apache2
---

### 2. Checked open ports
To verify if Apache is listening on port 80:
```bash
sudo ss -tulnp
---

### 3. Checked Apache configuration
To verify configuration errors:
```bash
sudo apachectl configtest
---

### 4. Started Apache service
To start the stopped web server
```bash
sudo systenmctl start apache2
---

### 5. Verified website
Opened in browser:

http://localhost
---

Key Learning
How to check service status using systemctl
How to check open ports using ss command
How to validate Apache configuration
Basic Linux server troubleshooting workflow
How to restore a stopped service

