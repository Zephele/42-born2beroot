# 42-born2beroot

![Debian](https://img.shields.io/badge/OS-Debian-red)
![42](https://img.shields.io/badge/School-42_SP-black)
![Status](https://img.shields.io/badge/Status-Finished-brightgreen)

## 📌 About
Born2beroot is a 42 project that introduces the world of virtualization and system
administration. The goal is to set up a virtual machine running Debian, following
strict rules about security, partitioning and services configuration.

## ⚙️ Configuration

### Virtual Machine
- **OS:** Debian (latest stable)
- **Virtualization:** VirtualBox

### Disk Partitioning
- Encrypted partitions using **LVM** (Logical Volume Manager)
- Separate partitions for `/`, `/home`, `/var`, `/tmp`, `/srv`, `/boot`

### Security
- **UFW** firewall — only port 4242 open
- **SSH** running on port 4242 — root login disabled
- **sudo** configured with strict rules:
  - Authentication limited to 3 attempts
  - Custom error message on wrong password
  - Inputs and outputs logged to `/var/log/sudo/`
  - TTY mode enabled
  - Restricted PATH for sudo

### Password Policy
- Minimum 10 characters
- Must contain uppercase, lowercase and a digit
- Maximum 3 consecutive identical characters
- Cannot contain the username
- Expires every 30 days
- Minimum 2 days before password can be changed
- Warning 7 days before expiration

### Monitoring Script
A `monitoring.sh` script runs every 10 minutes via **cron** and broadcasts system info to all terminals, including:
- OS and kernel version
- CPU (physical and virtual)
- RAM and disk usage
- CPU load
- Last reboot date
- LVM status
- Active connections and logged-in users
- Network info (IP and MAC)
- Number of sudo commands executed

## 📚 What I learned
- Linux system administration basics
- Virtual machine setup and configuration
- Disk partitioning and LVM
- Firewall and SSH configuration
- User and group management
- Shell scripting with cron jobs
- Security policies and best practices

## Author
**Rafael Tanaka** — [GitHub](https://github.com/Zephele) · [LinkedIn](https://www.linkedin.com/in/rafael-tanaka-359232285/)
