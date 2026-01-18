# Debian Office Server

## 📌 Overview
This project documents the design and implementation of a Debian 12–based
office server built from scratch to support internal file sharing,
user access control, and self-hosted collaboration services.

The server was designed for real office usage with a focus on
security, scalability, and maintainability.

---

## 🖥️ Environment
- Operating System: Debian 12
- Server Type: On-premise
- File System: EXT4
- Storage:
  - SSD: System & services
  - HDD 2TB: User data & shared resources

---

## 🧱 System Architecture
The server acts as a centralized office infrastructure node providing:
- Authentication & user separation
- File sharing for multiple divisions
- Private cloud services
- Secure remote access

Network exposure was initially handled using NAT and port forwarding,
then migrated to Cloudflare Tunnel to reduce public attack surface.

---

## 🔐 User & Group Management
- User accounts created per employee
- Group structure based on office divisions
- Private home directories for each user
- Shared directories controlled using Linux group permissions
- Fine-grained access control implemented using ACL

This approach ensures:
- Data separation between divisions
- Controlled access to shared resources
- Easier onboarding and permission management

---

## 🗄️ Storage Layout & Data Management
- System and services hosted on SSD for performance
- User data migrated to dedicated 2TB HDD
- Proper mount points with ownership and permission control
- Data migration performed without service disruption

Storage design focuses on:
- Scalability
- Data safety
- Clear separation between system and user data

---

## 📁 File Sharing
- Samba used as primary file sharing service
- Access controlled via Linux groups and ACL
- Combination of private and shared folders
- Integrated with existing user accounts

The file sharing setup supports daily office collaboration
while maintaining permission integrity.

---

## ☁️ Self-Hosted Services
- Initial deployment using OwnCloud
- Migrated to Nextcloud for improved features and maintainability
- Services deployed using Docker & Docker Compose
- Storage paths mapped to dedicated data disk

---

## 🌐 Networking & Remote Access
- Network configured using NetworkManager
- Initial public access via:
  - NAT on MikroTik router
  - Port forwarding on ISP router
  - Dynamic DNS using DuckDNS
- Final migration to Cloudflare Tunnel for:
  - Encrypted access
  - Reduced exposure of public ports
  - Improved security posture

---

## 🔐 Security Considerations
- Minimized exposed services to the public internet
- Internal services isolated from external access
- Tunnel-based access preferred over direct port forwarding
- Principle of least privilege applied to users and services

---

## 📡 Network Infrastructure (MikroTik)
- Router configured from scratch for office usage
- Bandwidth management implemented
- Dual-band wireless configuration
- Firewall rules applied for basic traffic filtering

---

## 🏢 Physical Infrastructure
- Server rack organization
- Cable management
- Integration with office CCTV system (Hikvision)

This supports operational reliability and easier maintenance.
