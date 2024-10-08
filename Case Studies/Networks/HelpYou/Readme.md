# 🌐 HelpYou IT: Advanced Networking Project

## 🎓 Course Integration
This project encapsulates two key subjects:
- ICTNWK529 Install and manage complex ICT networks
- ICTNWK546 Manage network security

## 🏗️ Project Objective
Build HelpYou IT from the ground up, implementing advanced networking protocols and standards using Cisco 1941 routers and 2940 switches hardware.

## 🖥️ Simulation & Real-World Implementation
- Complementary Cisco Packet Tracer (.pkt) files provided for vIOS simulation
- Network successfully deployed and tested on real hardware (Creation and Set-up Parts 1-7)
- Software side successfully implemented, mirroring a real-world environment (Creation and Set-up 8-10)

## 🛠️ Network Infrastructure

### Network Devices
- **Routers:** 
  - SB Router (South Bank - Head Office)
  - MG Router (Mt Gravatt - Branch Office)
- **Switches:** 
  - SB Switch (L2)

### Protocols & Services
- PPP Encapsulation
- OSPF Routing
- NAT (Network Address Translation)
- GRE Tunnel
- IPSec
- DHCP
- VoIP (IP Phones)
- CME (Call Manager Express)

## 💻 Operating Systems & Servers
- Windows PC
- Windows Server
- Ubuntu Server
- Domain Controllers (DC1 and DC2)

## 🌐 Network Services
- Proxy Server
- NTP (Network Time Protocol)
- DNS (Domain Name System)
- FTP (File Transfer Protocol)
- IIS (Internet Information Services)
- WSUS (Windows Server Update Services)

## 📂 Active Directory & Related Services
- Active Directory Domain Services (ADDS)
- Sites and Subnets Configuration
- Domain Controller Replication
- DFS (Distributed File System)
- FSRM (File Server Resource Manager)
- GPO (Group Policy Object)

## 🛡️ Security & Management Tools
- Anti-Virus Software Deployment
- PRTG (Network Monitoring Tool)
- Security Onion (Security Monitoring Tool)
- SNMP (Simple Network Management Protocol)
- Syslog

## 📁 Key Configuration Files
- `/etc/dhcp/dhcpd.conf`
- `/etc/default/isc-dhcp-server`

## 🔍 Troubleshooting Focus
- Network Symptoms Analysis
- Advanced Troubleshooting Techniques
- Network Diagnostic Utilities
- Structured Issue Resolution Process

## 🧪 Lab Modules

### Core Labs (1-7): Fundamental Networking Concepts
1. **PPP and OSPF Configuration**
   - PPP encapsulation on serial interfaces
   - OSPF routing setup and verification

2. **NAT and Proxy Server**
   - NAT configuration on routers
   - Proxy server installation and client setup

3. **Zone-Based Firewall (ZBF)**
   - Security zone creation and policy definition
   - Interface assignment and ZBF verification

4. **Advanced Routing**
   - Analysis of routing tables across network devices

5. **VPN and Tunneling**
   - IPSec VPN configuration
   - GRE tunnel setup with IPSec protection
   
   🎥 **Lab Demo Video**: [IPSec over GRE Tunnel Lab Setup](https://www.youtube.com/shorts/jG8KiPqzxY4)
   
   **Hardware Setup:**
   - Bottom of server rack: Cisco 2941 router
   - Top of server rack: Cisco 1941 router
   
   **Network Topology:**
   ```
   SB Router (South Bank - Head Office)
   - S0/0/0: 209.165.200.1/28
   - Tunnel 0: 172.16.12.1/30
   Model: Cisco 2941 (Top router)

   ISP Router
   - S0/0/0: 209.165.200.2/28
   - S0/0/1: 209.165.200.17/28
   - G0/0: 8.8.8.1/8
   Model: Cisco 2941 (Middle router)

   MG Router (Mt Gravatt - Branch Office)
   - S0/0/1: 209.165.200.18/28
   - Tunnel 0: 172.16.12.1/30
   - G0/1: 172.16.0.1/24
   Model: Cisco 1941 (Bottom router)
   ```

6. **DHCP Services**
   - DHCP server configuration on router and Ubuntu server
   - DHCP binding verification

7. **VoIP Implementation**
   - Cisco Call Manager Express (CME) setup
   - IP phone registration and testing

### Advanced Labs (8-10): Specialized Technologies and Services

8. **Windows Server and Active Directory** (with Sub-labs)
   1. Domain Controller Setup
   2. AD Sites and Subnets Configuration
   3. Domain Controller Replication
   4. DNS Integration with AD
   5. Distributed File System (DFS) Implementation
   6. File Server Resource Manager (FSRM) Setup
   7. Group Policy Object (GPO) for Desktop Management
   8. Anti-Virus Deployment via GPO
   9. Windows Server Update Services (WSUS) Configuration
   10. FTP Server Installation
   11. Ubuntu Integration with Active Directory

9. **Network Monitoring**
   - PRTG Network Monitor deployment
   - SNMP and Syslog sensor configuration

10. **Security Monitoring**
    - Security Onion installation and setup
    - Network traffic analysis and security event monitoring

## 📝 Documentation Requirements
- Detailed screenshots of configurations and outputs
- Concise descriptions of key concepts
- Comprehensive troubleshooting report

## 📞 Contact Information
For further queries or clarification, please contact:
**Thomas McGhee**
Email: thomas.mcghee@connect.qut.edu.au
