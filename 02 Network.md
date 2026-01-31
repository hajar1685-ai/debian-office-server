# 🌐 Network Infrastructure Documentation

## 📌 Overview
This document describes the design, configuration, and implementation of
an **office network infrastructure built from scratch to production-ready**.

The network is tightly integrated with a **Debian 12 Server** that provides
file sharing, private cloud services, and centralized user management.
The main goals are **stability, security, and controlled public access**.

---

## 🧱 Network Topology

**Main network flow:**

Internet  
→ ISP Router  
→ MikroTik Router  
→ Debian 12 Server  
→ Internal Clients (Office Users & Devices)

---

## 🔧 Network Components

### 🔹 MikroTik Router
Acts as the **core network gateway**, responsible for:
- NAT & Port Forwarding
- Bandwidth Management
- Firewall & Traffic Filtering
- Dual-band Wireless (2.4 GHz & 5 GHz)

### 🔹 Debian 12 Server
Functions as:
- File Server (Samba)
- Private Cloud (OwnCloud / Nextcloud)
- Database Server (MariaDB)
- Application Server (PHP)
- Centralized User & Permission Management

---

## 🌍 Internet Access & Public Exposure

### 1️⃣ NAT & Port Forwarding
- NAT configured on MikroTik
- Port forwarding from ISP router to MikroTik
- Controlled public access to internal services

### 2️⃣ Dynamic DNS (DuckDNS)
Initially used to:
- Map a dynamic public IP to a domain
- Enable external access testing

### 3️⃣ Cloudflare Tunnel (Final Implementation)
Migrated to **Cloudflare Tunnel** to:
- Eliminate exposed open ports
- Provide public access without revealing server IP
- Enable TLS encryption & Zero Trust security
- Restrict access to authorized internal users

---

## 🔐 Network Security Implementation

### 🔒 Firewall (MikroTik)
- Drop invalid and suspicious connections
- Restrict router management access
- Isolate internal and public traffic
- Protect server from brute-force attempts

### 🔑 Access Control
- No direct public exposure of the server
- Application access via Cloudflare Tunnel only
- Service access based on user roles

---

## 📶 Bandwidth Management

- Bandwidth allocation per user or department
- Prevents single users from saturating the link
- Optimized for small-to-medium office environments

---

## 👥 User & Department Segmentation

### 🔹 User Grouping
- Users are created based on **department structure**
- Each department has:
  - Defined network access
  - Dedicated server folders
  - Permission rules using ACL

### 🔹 Server Integration
- Network users integrated with:
  - Samba File Server
  - Linux permissions & ACL
  - Internal application access

---

## 🗄️ Storage & Network Integration

- 2TB HDD used as shared network storage
- Permanently mounted on Debian Server
- ACL-based access aligned with department structure
- Data migration performed without service downtime

---

## 📡 Supported Network Services

- File Sharing (Samba)
- Private Cloud (Nextcloud)
- Database Services (MariaDB)
- Secure Remote Access
- Internal Office Networking

---

## 🧠 Skills Demonstrated

✔ Network Design & Implementation  
✔ MikroTik Configuration  
✔ NAT, Firewall, and Bandwidth Management  
✔ Secure Public Access (Cloudflare Tunnel)  
✔ Linux Network Integration  
✔ Office Infrastructure Deployment  
✔ Troubleshooting & Data Migration  

---

## 🎯 Career Relevance

This project is highly relevant for roles such as:
- **NOC Engineer**
- **Network Engineer**
- **Linux System Administrator**
- **Junior to Mid-Level DevOps Engineer**

---

## 📌 Notes
All configurations were performed **manually and hands-on** to gain
a deep understanding of networking concepts and infrastructure design.

---

📫 **Author**  
GitHub: https://github.com/hajar1685-ai
