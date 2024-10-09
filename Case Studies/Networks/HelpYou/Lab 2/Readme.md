# 🔐 Lab 2 Documentation: Zone-Based Firewall Configuration

## 🎓 Project Overview
This lab demonstrates the implementation of a Zone-Based Firewall (ZBF) to secure communications between trusted and untrusted network zones. The network includes an ISP, SB (South Bank - Head Office), and MG (Mt Gravatt - Branch Office), with ZBF configured to control traffic across these sites. The focus is on controlling traffic flows between the WAN and internal LANs, using security policies to inspect and regulate traffic.

## 🛠️ Network Infrastructure

### **Devices and Topology**
- **ISP Router**: The backbone of the WAN, responsible for routing external traffic.
- **SB Router**: The head office router, which manages VLAN segmentation for various departments.
- **MG Router**: The branch office router, handling local office LAN and WAN communications.

## 🔄 Key Features

### **Zone-Based Firewall Configuration**
- **Security Zones**: The firewall setup divides the network into trusted (Inside) and untrusted (Internet) zones.
- **Traffic Inspection**: ZBF allows dynamic handling of return traffic by inspecting traffic flow between zones.
- **Policy-Based Filtering**: Define specific traffic policies between zones, allowing only approved protocols and traffic to flow.

#### Lab 2: Zone-Based Firewall Setup
- **Part 1**: Configure security zones for SB and MG routers.
- **Part 2**: Create traffic inspection policies using class-maps and policy-maps.
- **Part 3**: Define and assign zone pairs to control traffic flow between the Inside and Internet zones.

#### Configuration Highlights:

- **SB Router Configuration**:
   ```bash
   zone security Inside
   zone security Internet
   ```

- **MG Router Configuration**:
   ```bash
   zone-pair security Inside-to-Internet
   service-policy type inspect Inside-to-Internet
   ```

## 🌐 Network Services and Security

- **Zone-Based Policy Firewall**: Provides granular control of traffic between the trusted internal network and the external Internet.
- **NAT (Network Address Translation)**: Used for managing traffic from the MG router to the Internet.
- **Access Control Lists (ACLs)**: Employed for additional traffic filtering.

## 🔍 Lab Modules Overview

1. **Module 1: Security Zone Creation** (SB and MG Routers)
   - Define trusted and untrusted zones for traffic control.
2. **Module 2: Traffic Inspection Policies**
   - Create class-maps to inspect TCP, UDP, and ICMP traffic.
3. **Module 3: Apply Zone Pairs and Verification**
   - Assign zone pairs and verify the firewall setup using ping tests and security checks.

## 🛡️ Security Focus
- **Dynamic Traffic Inspection**: ZBF policies allow dynamic tracking of return traffic, enhancing network security.
- **Strict Zone Policies**: Enforces a deny-all rule by default, only allowing traffic explicitly permitted by policy-maps.

## 📋 Documentation Requirements
- **Detailed Screenshots**: Capture outputs of zone pairs, traffic inspection, and policy-maps.
- **Troubleshooting Reports**: Include diagnostic commands and resolutions for configuration errors.

## 📧 Contact Information
For further queries or support, feel free to reach out:
**Thomas McGhee**  
Email: thomas.mcghee@connect.qut.edu.au

