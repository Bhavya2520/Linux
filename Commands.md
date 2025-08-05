# 🐧 Linux Commands for DevOps

This guide lists essential Linux commands specifically useful in DevOps practices, organized by functional category.

---

## 📁 File and Directory Management
- `ls` – List directory contents  
- `cd` – Change directory  
- `pwd` – Print working directory  
- `cp` – Copy files and directories  
- `mv` – Move or rename files and directories  
- `rm` – Remove files or directories  
- `mkdir` – Make directories  
- `rmdir` – Remove empty directories  
- `touch` – Create empty files  
- `find` – Search for files  
- `tree` – View directory structure  
- `chmod` – Change file permissions  
- `chown` – Change file ownership  

---

## 📄 File Viewing & Text Processing
- `cat` – View file content  
- `less` – Scroll through file interactively  
- `head` – View beginning of a file  
- `tail` – View end of a file (useful for logs)  
- `grep` – Search patterns in files  
- `sed` – Stream editor for modifying file content  
- `awk` – Pattern scanning and text processing  
- `cut` – Remove sections from lines  
- `sort` – Sort file contents  
- `uniq` – Filter duplicate lines  

---

## 🔄 Process Management
- `ps` – View running processes  
- `top` – Live view of system processes  
- `htop` – Enhanced process viewer  
- `kill` – Terminate a process by PID  
- `killall` – Terminate all processes by name  
- `jobs` – List background jobs  
- `bg` – Resume a job in background  
- `fg` – Bring a job to foreground  
- `nice` / `renice` – Manage process priority  
- `time` – Measure execution time  

---

## 💽 Disk & Filesystem Management
- `df` – Show disk space usage  
- `du` – Estimate file/folder space  
- `lsblk` – List block devices  
- `mount` / `umount` – Mount or unmount filesystems  
- `blkid` – Print block device info  
- `fsck` – Filesystem check and repair  

---

## 🌐 Networking Commands
- `ip` – View/manipulate IP addresses and routes  
- `ping` – Check connectivity  
- `ss` – View socket stats (modern replacement for `netstat`)  
- `traceroute` – Trace packet path  
- `dig` – DNS lookup  
- `wget` – Download from the web  
- `curl` – Transfer data via HTTP/FTP/etc.  
- `scp` – Securely copy files between systems  
- `ssh` – Remote secure login  

---

## 📦 Package Management
> Use according to your distro (Debian/Ubuntu vs RHEL/CentOS)

- `apt-get`, `apt-cache`, `dpkg` – Debian-based systems  
- `yum`, `dnf`, `rpm` – RHEL/CentOS systems  

---

## 🔁 Scheduling Tasks
- `crontab` – Schedule recurring tasks  
- `at` – Schedule one-time tasks  
- `sleep` – Delay execution (used in scripts)  

---

## 🔐 Permissions & Security
- `chmod` – Change permission  
- `chown` – Change ownership  
- `chgrp` – Change group ownership  
- `sudo` – Execute command as another user  
- `umask` – Set default permissions  

---

## 🧠 System Monitoring & Info
- `uname` – System info  
- `hostname` – Get or set hostname  
- `uptime` – System uptime  
- `free` – Memory usage  
- `dmesg` – Boot & kernel messages  
- `vmstat` – System performance  
- `lscpu` – CPU info  
- `watch` – Run a command repeatedly  

---

## 🧪 Troubleshooting & Diagnostics
- `lsof` – List open files  
- `strace` – Trace system calls  
- `journalctl` – View systemd logs  
- `iostat`, `mpstat`, `pidstat` – Advanced system stats  

---

## 🔁 Backup & File Transfer
- `rsync` – Sync files and directories  
- `scp` – Secure file copy  
- `tar`, `gzip`, `zip` – Archive and compress files  

---

## 🔧 Services & Daemons
- `systemctl` – Manage system services  
- `service` – Older service management  

---

## ⚙️ Shutdown & Reboot
- `shutdown` – Schedule system shutdown  
- `reboot` – Reboot system  
- `halt`, `poweroff` – Halt or power off the system  
