
# 🌐 Lab 1 Documentation
## 🎓 Project Overview
This portfolio project demonstrates a comprehensive network design and configuration setup spanning multiple locations, utilizing advanced networking concepts and protocols. The setup includes ISP, SB (South Bank - Head Office), and MG (Mt Gravatt - Branch Office) sites, configured with Cisco 1941 routers and switches, designed for real-world implementation.

## 🛠️ Network Infrastructure

### **Devices and Topology**
- **ISP Router** (Backbone of the WAN)
  - Interfaces: S0/0/0 to SB, S0/0/1 to MG
  - Routing and PPP Configuration with CHAP authentication
- **SB Router** (Head Office)
  - Interfaces: G0/0 for VLANs, S0/0/0 for WAN to ISP
  - VLAN Configuration and Router-on-a-Stick setup
- **MG Router** (Branch Office)
  - Interfaces: G0/0 for LAN, S0/0/1 for WAN to ISP

## 🔄 Key Features

### **Routing and WAN Configuration**
- **WAN Protocols:**
  - **PPP Encapsulation with CHAP Authentication** across serial links
  - **IP Routing:** Configured on all devices with static routes for simplicity

#### Lab 1: WAN Setup
- **Part 1:** ISP Router WAN Interface Configuration
- **Part 2:** SB Router WAN Interface Configuration
- **Part 3:** MG Router WAN Interface Configuration
- **Part 4:** Verification of WAN connectivity

#### Configurations:

- **ISP Router Configuration**:
  ```bash
  int s0/0/0
  ip address 209.165.200.2 255.255.255.240
  encapsulation ppp
  ppp authentication chap
  no shut
  ```

- **SB Router WAN Configuration**:
  ```bash
  int s0/0/0
  ip address 209.165.200.1 255.255.255.240
  encapsulation ppp
  ppp authentication chap
  no shut
  ```

- **MG Router WAN Configuration**:
  ```bash
  int s0/0/1
  ip address 209.165.200.18 255.255.255.240
  no shut
  ```

### **LAN and VLAN Configuration**

#### Lab 2: VLAN Setup
- **Part 1:** SB Router VLAN Configuration
- **Part 2:** MG Router LAN Configuration

- **SB Router - VLANs**:
  - **VLAN 20 (Customer Service)** - 192.168.20.1/27
  - **VLAN 30 (Marketing)** - 192.168.30.1/27
  - **VLAN 90 (Servers)** - 192.168.90.1/29

  ```bash
  int g0/0.20
  encapsulation dot1q 20
  ip address 192.168.20.1 255.255.255.224
  ```

- **MG Router - LAN Configuration**:
  - **LAN Interface:** G0/0 configured with subnet 172.16.0.1/24
  ```bash
  int g0/0
  ip address 172.16.0.1 255.255.255.0
  no shut
  ```

## 🔍 Detailed Configurations

### **ISP Router Configuration**
- Serial connections between ISP and SB, and ISP and MG, configured with PPP encapsulation and CHAP authentication for secure data transmission.
  
### **SB Router - Router on a Stick**
- Configured with trunk ports and multiple sub-interfaces for each VLAN to support different departments like Customer Service, Marketing, and Servers.

### **MG Router Configuration**
- MG Router is the branch office device, handling both WAN and LAN traffic with interfaces defined for communication with the ISP and the internal office LAN.

## 🌐 Network Protocols & Services
- **PPP (Point-to-Point Protocol):** for secure communication over WAN links.
- **CHAP Authentication:** Ensures secure routing between ISP and routers.
- **VLAN Segmentation:** Separate VLANs for different departments with IP assignments.

## 📋 Lab Modules Overview

1. **Module 1: WAN Configuration** (ISP to SB, ISP to MG)
   - PPP, CHAP authentication setup
2. **Module 2: VLAN and Router-on-a-Stick Setup** (SB Router)
   - VLANs for different services and departments
3. **Module 3: MG WAN and LAN Configuration**
   - WAN to ISP, LAN for internal office communication

## 🛡️ Security Focus
- **CHAP Authentication** between routers ensures that all data transmitted over WAN links is secure.
- **VLANs** provide network segmentation to isolate different types of traffic (e.g., office, server, marketing).

## 📂 Configuration Highlights

### **SB Switch Configuration**
#### SB Step 
```bash


```
#### SB Switch Step 2
```bash
Step 2. Configure the SB Router’s LAN interface G0/0 with router-on-a-stick configuration to cater for three VLANs at the same time. 
Assign the subinterfaces with IP address according to the aforementioned ip address table.


!###Configuring the hostname of SB-S1###!
en
conf t
hostname SB-S1


!### Initializing G0/1 - Goes to SB###!
int g0/1
switchport mode trunk
no shut
exit
!###Initializing Vlans###!

!###Initializing CS VLAN###!
int vlan 20
exit
!###Initializing Marketing VLAN###!
int vlan 30
exit
!###Initializing Server VLAN###!
int vlan 90
exit
!###Naming Vlans###!
!###Naming vlan 20###!
vlan 20
name CS
!###Naming vlan 30###!
vlan 30
name Marketing
!###Naming vlan 90###!
vlan 90
name Server

!###Configuring port ranges to co-incide with VLAN ranges###!
!###Configuring VLAN 20###!
int range fastEthernet0/1-8
description CS
switchport mode access
switchport access vlan 20
no shut
exit
!###Configuring VLAN 30###!
int range fastEthernet0/9-17
description Marketing
switchport mode access
switchport access vlan 30
no shut
exit
!###Configuring VLAN 90###!
int range fastEthernet0/18-24
description Server
switchport mode access 
switchport access vlan 90
no shut
exit

```

### **SB Router Configuration**
```bash
Step 2. Configure the SB Router’s LAN interface G0/0 with router-on-a-stick configuration to cater for three VLANs at the same time. 
Assign the subinterfaces with IP address according to the aforementioned ip address table. 

!###Configuring Router SB###!
en
conf t
hostname SB

!###Configuring G0/0 interface to up state###!
int g0/0
no shut

!### Configuring virtual routing interface for each Vlan###!
!##########################VLAN20##########################!
!####################VLAN 20 Has 40 PCs####################!
int g0/0.20
encapsulation dot1q 20
ip address 192.168.20.1 255.255.255.224
exit
!##########################VLAN20##########################!
!####################VLAN 30 Has 40 PCs####################!
int g0/0.30
encapsulation dot1q 30
ip address 192.168.30.1 255.255.255.224
exit
!##########################VLAN20##########################!
!####################VLAN 90 Has 5 PCs#####################!
int g0/0.90
encapsulation dot1q 90
ip address 192.168.90.1 255.255.255.248
exit
!###Showing Route table for confirmation###!
do sh ip route
!##########################################################!
!###Showing ip interfaces configuration####!
do sh ip int br
!###Part 1: Cable the network and configure the devices IP address!
!###STEP 2 Successfully completed!###!
```

## 📝 Project Documentation
- **Files**: Detailed command line configurations and explanations are included for each step of the project setup.
- **Troubleshooting**: Focus on diagnostic utilities, detailed output verifications, and structured problem-solving processes.

## 📧 Contact Information
For further queries or support, feel free to reach out:
**Thomas McGhee**  
Email: thomas.mcghee@connect.qut.edu.au
