# 🌐 Lab 4 Documentation: GRE Tunnel Configuration

## 🎓 Project Overview
This lab focuses on configuring a VPN using a GRE (Generic Routing Encapsulation) tunnel to connect two separate sites securely. The network consists of the ISP, SB Router (representing the head office at South Bank), and MG Router (representing the branch office at Mt Gravatt). The aim is to establish a secure GRE tunnel between SB and MG routers, ensuring that the devices from both LANs can communicate seamlessly, despite the ZBF (Zone-Based Firewall) blocking internet-initiated traffic.

## 🛠️ Network Infrastructure

### **Devices and Topology**
- **ISP Router**: Connects the external Internet and acts as the backbone for WAN connections.
- **SB Router**: Head office router at South Bank, configured with GRE tunnel endpoint.
- **MG Router**: Branch office router at Mt Gravatt, configured with GRE tunnel endpoint.

## 🔄 Key Features

### **GRE Tunnel Configuration**
- **Secure Communication**: GRE tunnel provides a virtual point-to-point link, enabling secure communication between the two sites.
- **Trusted Zones**: The tunnel interfaces on both SB and MG routers are configured as trusted Inside zone-members, allowing seamless communication between LAN devices.
- **Traffic Routing**: GRE tunnels enable encapsulation of packets, allowing different LANs to communicate through a shared WAN infrastructure.

#### Lab 4: GRE Tunnel Setup
- **Part 1**: Network Setup and Device Configuration
  - Set up network cabling, restore the running configurations from backups, and verify basic connectivity.
- **Part 2**: GRE Tunnel Configuration
  - Create a GRE tunnel interface on both SB and MG routers, and configure the tunnel endpoints.
- **Part 3**: Routing over the GRE Tunnel
  - Enable OSPF routing over the GRE tunnel, allowing LAN devices to communicate transparently.

#### Configuration Highlights:

- **SB Router GRE Tunnel Configuration**:
  ```bash
  interface Tunnel0
  ip address 172.16.12.1 255.255.255.252
  tunnel source Serial0/0/0
  tunnel destination 209.165.200.18
  ```

- **MG Router GRE Tunnel Configuration**:
  ```bash
  interface Tunnel0
  ip address 172.16.12.2 255.255.255.252
  tunnel source Serial0/0/1
  tunnel destination 209.165.200.1
  ```

## 🌐 Network Services and Security

- **GRE Tunnel**: Provides encapsulation of packets to ensure communication between SB and MG LANs as if they were part of the same network.
- **Zone-Based Firewall (ZBF)**: ZBF rules are configured to block internet-initiated traffic, while allowing trusted tunnel communication.
- **OSPF Routing**: Configured to enable dynamic routing between the SB and MG LANs over the GRE tunnel.

## 🔍 Lab Modules Overview

1. **Module 1: Network Setup**
   - Restore network configuration from previous backups and verify connectivity.
2. **Module 2: GRE Tunnel Configuration**
   - Set up GRE tunnel interfaces on both SB and MG routers, and configure trusted zones.
3. **Module 3: OSPF Routing Configuration**
   - Configure OSPF on SB and MG routers to enable dynamic routing over the GRE tunnel.

## 🛡️ Security Focus
- **Zone-Based Firewall (ZBF)**: Ensures that internet-initiated traffic is blocked by default, while the GRE tunnel provides a trusted link for internal LAN communication.
- **GRE Tunnel Security**: Although GRE itself does not provide encryption, the trusted nature of the tunnel allows for secure internal routing. For further encryption, IPSec can be implemented (explored in later labs).

## 📋 Documentation Requirements
- **Screenshots**: Capture tunnel interface configurations, OSPF routing tables, and successful pings between SB and MG LANs.
- **Verification Reports**: Include details of connectivity tests, routing tables, and tunnel status verification.

## 📧 Contact Information
For further queries or support, feel free to reach out: **Thomas McGhee**  
Email: [thomas.mcghee@connect.qut.edu.au](mailto:thomas.mcghee@connect.qut.edu.au)

