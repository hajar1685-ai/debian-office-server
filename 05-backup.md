# 💾 Backup, Recovery & Data Protection Strategy

## 📌 Overview
This document describes the **backup, recovery, and data protection strategy**
implemented on a **Debian 12 server infrastructure** built from scratch.

The main objectives are:
- Data availability and integrity
- Protection against hardware failure
- Scalability for future storage expansion

---

## 🗂️ Data Classification

### 🔹 Critical Data
- User shared files (Samba)
- Private cloud application data (Nextcloud)
- MariaDB databases
- System configuration files (`/etc`)
- User data with ACL-based permissions

### 🔹 Non-Critical Data
- Application cache
- Temporary files
- Containers and images that can be rebuilt

---

## 🧱 Storage Architecture

### 🔹 Current Architecture
- Operating system installed on SSD
- User and application data stored on dedicated HDD(s)
- Separation between system and data partitions

### 🔹 Future Storage Plan
- Implementation of **RAID 1 (Mirroring)** for critical data
- Flexible HDD capacity (not limited to a specific size)
- Designed to support gradual storage expansion

### 🔹 RAID 1 Benefits
- Data remains available if one disk fails
- Minimal downtime during disk replacement
- Suitable for office servers and private cloud environments

---

## 🔄 Backup Method

### 🔹 Manual Backup (Current Implementation)
Backups are currently performed manually using:
- `rsync`
- `tar`

Backup targets include:
- User home directories
- Samba shared folders
- Application data directories
- Critical system configuration files

File ownership, permissions, and ACLs are preserved.

---

## 📁 Backup Scope

- `/home`
- Application data directories
- Shared storage directories
- Important system configuration files

---

## 🛢️ Database Backup

### 🔹 MariaDB
Databases are backed up using `mysqldump`
and stored separately from application data.

Example:
```bash
mysqldump -u root -p database_name > database_backup.sql
