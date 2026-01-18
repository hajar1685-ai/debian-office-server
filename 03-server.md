# 🖥️ Server Infrastructure Documentation

## 📌 Overview
This document describes the complete setup and management of a **Debian 12 Server**
built from scratch and used as the **core infrastructure server** for an office
environment.

The server is designed to be **stable, secure, and scalable**, supporting
file sharing, private cloud services, database services, and centralized
user access control.

---

## 🐧 Operating System

- OS: **Debian GNU/Linux 12 (Bookworm)**
- Installation Type: Minimal installation
- Kernel: Default Debian stable kernel
- Filesystem: EXT4
- Server Role: Multi-purpose Infrastructure Server

---

## 🧱 Server Architecture

### Main Roles
- File Server (Samba)
- Private Cloud Server (Nextcloud / OwnCloud)
- Database Server (MariaDB)
- Web Application Server (PHP 8)
- Authentication & Permission Control
- Network-integrated Infrastructure Node

---

## 💾 Storage Configuration

### 🔹 Physical Storage
- Primary Disk: OS & system services
- Secondary Disk: **2TB HDD** for shared data

### 🔹 Mounting Strategy
- Secondary disk permanently mounted via `/etc/fstab`
- Dedicated mount point for shared data
- Verified persistence after reboot

### 🔹 Data Migration
- User data migrated from SSD to HDD
- Migration performed without service downtime
- Permissions preserved during migration

---

## 👥 User & Group Management

### 🔹 User Creation
- Users created manually using Linux user management tools
- Each user assigned:
  - Home directory
  - Secure password
  - Department-based group

### 🔹 Group Structure
- Groups represent **office departments**
- Examples:
  - `office-qc`
  - `office-admin`
  - `office-it`

### 🔹 Permission Model
- Linux permissions + ACL (Access Control List)
- Fine-grained access per folder
- No shared access without explicit permission

---

## 📂 File Sharing (Samba)

### 🔹 Samba Configuration
- Samba installed and configured manually
- Integrated with Linux users & groups
- Secure authentication using SMB passwords

### 🔹 Share Types
- Private user folders
- Department shared folders
- Restricted access based on group membership

### 🔹 Security
- No guest access
- Read/write permissions controlled via ACL
- Server-side permission enforcement

---

## ☁️ Private Cloud Service

### 🔹 Nextcloud / OwnCloud
- Installed on Debian Server
- PHP 8 configured for performance & compatibility
- Data directory moved to secondary HDD

### 🔹 Access Model
- Internal access for office users
- External access via **Cloudflare Tunnel**
- No direct port exposure to the public internet

---

## 🗄️ Database Server

### 🔹 MariaDB
- Used by cloud applications
- Secured with strong credentials
- Local-only access (not publicly exposed)

---

## 🌐 Network Integration

- Static local IP address
- Integrated behind MikroTik Router
- NAT & Firewall handled at network gateway
- Secure public access through Cloudflare Tunnel

---

## 🔐 Server Security

### 🔹 System Hardening
- Minimal installed packages
- Unused services disabled
- Regular system updates

### 🔹 Access Control
- SSH access restricted
- Root login disabled (recommended)
- Role-based file access

### 🔹 Public Exposure
- No open ports directly to the server
- All public services routed via Cloudflare Tunnel

---

## ⚙️ Service Management

- Services managed using `systemctl`
- Logs monitored for stability and errors
- Controlled service restarts during maintenance

---

## 🧠 Skills Demonstrated

✔ Debian Server Installation & Administration  
✔ Linux User & Group Management  
✔ ACL-based Permission Design  
✔ Samba File Server Deployment  
✔ Cloud Storage Deployment  
✔ Storage Migration & Mounting  
✔ Secure Server Hardening  
✔ Infrastructure Troubleshooting  

---

## 🎯 Career Relevance

This server project demonstrates real-world skills for:
- **Linux System Administrator**
- **Network Engineer**
- **NOC Engineer**
- **DevOps (Infrastructure-focused)**

---

## 📌 Notes
All configurations were implemented **manually without automation tools**
to ensure deep understanding of Linux server internals and infrastructure
design principles.

---

📫 **Author**  
GitHub: https://github.com/hajar1685-ai
