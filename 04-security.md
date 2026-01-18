# 🔐 Security & Hardening Documentation

## 📌 Overview
This document describes the **security practices and hardening steps**
implemented on the Debian 12 infrastructure server to ensure
**confidentiality, integrity, and availability** of services and data.

All configurations were applied with a **security-first approach**,
especially for servers exposed to public access.

---

## 🛡️ Operating System Hardening

### 🔹 Minimal Installation
- Debian 12 installed with minimal packages
- Unnecessary services removed or disabled
- Reduced attack surface

### 🔹 System Updates
- Regular security updates using `apt`
- Kernel and package updates applied manually
- System reboot scheduled during maintenance windows

---

## 🔑 User Access Control

### 🔹 SSH Access
- SSH access restricted to authorized users only
- Root login disabled via SSH
- Password authentication limited (key-based access recommended)

### 🔹 User Privileges
- No shared user accounts
- Least-privilege principle applied
- Administrative access granted only when required

---

## 🧱 Firewall & Network Security

### 🔹 Network Segmentation
- Server placed behind MikroTik Router
- Internal services not directly accessible from the internet

### 🔹 Firewall Strategy
- Firewall rules enforced at network gateway (MikroTik)
- Only required traffic allowed
- Unused ports blocked by default

---

## ☁️ Secure Public Access

### 🔹 Cloudflare Tunnel
- Public access handled via Cloudflare Tunnel
- No direct port forwarding to server
- Origin server IP hidden from public exposure

### 🔹 Benefits
- Protection against direct attacks
- TLS encryption handled by Cloudflare
- Reduced risk of DDoS and port scanning

---

## 📂 File System Security

### 🔹 Permission Model
- Strict Linux permissions applied
- ACL (Access Control List) used for fine-grained access
- No world-writable directories

### 🔹 Shared Resources
- Samba shares restricted by user & group
- Authentication required for all shared folders
- Access logged and controlled

---

## 🗄️ Application Security

### 🔹 Database (MariaDB)
- Database not exposed publicly
- Strong credentials enforced
- Access limited to localhost or internal services only

### 🔹 Web Applications
- PHP configured securely
- File upload restrictions applied
- Data directories separated from system partitions

---

## 📜 Logging & Monitoring

### 🔹 System Logs
- Logs reviewed regularly via `journalctl`
- Service logs monitored for errors or anomalies

### 🔹 Access Monitoring
- SSH login attempts monitored
- Failed authentication attempts reviewed

---

## 🔒 Backup & Data Protection

### 🔹 Data Integrity
- Critical data stored on dedicated storage
- Permissions preserved during data migration

### 🔹 Backup Strategy (Planned / Partial)
- Manual backups for important data
- Future plan: automated backups with verification

---

## 🚨 Incident Response (Basic)

- Unauthorized access attempts investigated
- Services isolated if suspicious activity detected
- Logs preserved for analysis

---

## 🧠 Security Skills Demonstrated

✔ Linux Server Hardening  
✔ Secure SSH Configuration  
✔ Firewall & Network Security Principles  
✔ Zero Trust Access via Cloudflare Tunnel  
✔ ACL & Permission-Based Security  
✔ Secure Database Deployment  
✔ Incident Awareness & Logging  

---

## 🎯 Career Relevance

This security implementation is relevant for:
- **Linux System Administrator**
- **Network Security Engineer**
- **NOC Engineer**
- **DevOps (Infrastructure Security)**

---

## 📌 Notes
All security measures were applied **manually without automation**
to ensure deep understanding of Linux security fundamentals and
real-world infrastructure protection.

---

📫 **Author**  
GitHub: https://github.com/hajar1685-ai
