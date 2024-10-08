# README for Cloud Network Implementation with code - Daydreams Travel Agency
## ICTCLD505 AT2 Implement cloud infrastructure with code
## Overview

This document provides a comprehensive overview of the virtual network implementation for **Daydreams Travel Agency**, outlining the strategic move from on-site operations to a cloud-based infrastructure. The project encompasses the design, configuration, and implementation of an AWS-based virtual network that meets the current and future business needs of Daydreams Travel Agency, ensuring scalability, security, and high availability.

---

## Project Title
**Virtual Network Implementation for Daydreams Travel Agency**

### Project Scope
The project aims to:
- Migrate the existing on-premises network infrastructure of Daydreams Travel Agency to a cloud-based solution on **Amazon Web Services (AWS)**.
- Design and implement a virtual network that supports up to 30 employees, including on-site and remote workers.
- Ensure the network architecture is scalable, highly available, and secure, meeting both current operational needs and future expansion requirements.

---

## Components and Architecture

### 1. **Cloud Resources**

The project utilized various AWS cloud services to build a multi-tier architecture, ensuring a secure, scalable, and flexible solution for the business. Below is a list of key services used in the implementation:

- **Amazon S3**: Cloud-based storage solution for scalable and durable storage needs.
- **Amazon EC2**: Scalable virtual machines used for hosting application servers, web services, and providing computing power.
- **AWS VPC**: Provides network isolation, allowing segmentation of network resources across private and public subnets.
- **AWS Shield & WAF**: Protection from DDoS attacks and web-based exploits.
- **Amazon RDS**: Managed relational database service for high availability and disaster recovery.
- **AWS VPN**: Secured remote access for employees, ensuring private network communication for work-from-home personnel.
- **Amazon IAM & KMS**: Identity and access management to enforce strict access controls and encryption of sensitive data.
- **Amazon CloudWatch**: Centralized logging and monitoring of all resources to ensure optimal performance and security.
- **AWS Direct Connect**: High-speed, low-latency connection between the company’s network and AWS.

### 2. **Network Architecture**

The network topology consists of multiple subnets, split into private and public zones, all configured within an AWS Virtual Private Cloud (VPC). The logical design includes the following:

- **Public Subnets**: These host resources that need to be publicly accessible, such as bastion hosts and web servers.
- **Private Subnets**: These are reserved for backend services, including databases and internal application servers.
- **NAT Gateway**: Allows resources in private subnets to access the internet securely without being exposed.
- **VPC Peering**: Set up between multiple VPCs to allow inter-VPC traffic using private IPv4 addresses.
- **Route Tables**: Configured to manage traffic flow between subnets, ensuring secure communication between public and private subnets.

---

## Key Business Requirements and Solutions

### 1. **Business Needs:**
- **Increased Storage Capacity**: Implemented with **Amazon S3**.
- **Scalable Computing Power**: Achieved using **Amazon EC2** instances.
- **Network Security and Redundancy**: Addressed through **AWS Shield, Route 53**, and strict security group policies.
- **Remote Access**: Secure remote worker connectivity enabled via **AWS VPN** and **Direct Connect**.
- **High Availability & Disaster Recovery**: Utilized **Amazon RDS** with **Multi-AZ deployment** for database resilience.
- **Data Privacy & Compliance**: Enforced through **AWS IAM** and **KMS** to manage access control and encryption.

### 2. **Compliance with Industry and Legislative Requirements:**
- **Australian Travel Accreditation Scheme (ATAS)**: Ensured compliance with travel industry standards.
- **Australian Consumer Law (ACL)**: Implemented systems that meet consumer protection laws.
- **Quality Tourism Framework**: The virtual infrastructure meets high operational standards to align with industry accreditation.

---

## Security Measures

To safeguard Daydreams Travel Agency’s data and infrastructure, several layers of security have been implemented:
- **IAM Role-Based Access Control (RBAC)**: Used to enforce least privilege access.
- **KMS-Managed Encryption**: All sensitive data is encrypted at rest and in transit using KMS.
- **AWS Shield & WAF**: Active protection against DDoS attacks and web exploits.
- **Amazon VPC Isolation**: Logical segmentation of network resources to minimize attack surfaces.
- **Amazon CloudWatch**: Real-time monitoring and alerting for potential security breaches.

---

## Testing & Validation

### 1. **Traffic Flow Validation:**
Network traffic was tested to ensure proper flow between the virtual network and external resources:
- **Ping Tests**: Confirmed successful ICMP traffic flow to the public EC2 instance.
- **NAT Gateway Validation**: Confirmed that internal EC2 instances in private subnets can access the internet through the NAT gateway without direct exposure.
- **VPC Peering**: Ensured inter-VPC communication using private IPs, with successful routing via updated route tables.

### 2. **Security Testing:**
- **Penetration Testing**: Simulated attacks were conducted to validate firewall rules and security group configurations.
- **CloudWatch Logs**: Used for real-time log collection and analysis to detect anomalies in traffic and access patterns.

---

## Challenges and Solutions

### Major Challenge: Routing Table Configuration for VPC Peering
- **Problem**: Incorrect routing tables initially caused communication issues between the peered VPCs.
- **Solution**: Reconfigured the routing tables to correctly point to the appropriate CIDR blocks of the peer VPC, ensuring seamless traffic flow between VPCs.

---

## Automation & Future Improvements

### 1. **Automation Opportunities:**
To streamline operations and minimize manual intervention, several automation techniques have been proposed:
- **CloudFormation Templates**: Use AWS CloudFormation to automate the deployment of network resources.
- **Auto Scaling**: Implement auto-scaling policies for EC2 instances to dynamically adjust to traffic demands.
- **Automated Backups**: Scheduled automated backups for EC2 instances and RDS databases using **AWS Backup**.

### 2. **Future Scaling:**
- **Multi-Region Setup**: Expand the VPC design to support multi-region deployment for better disaster recovery and reduced latency for global clients.
- **Serverless Architecture**: Explore the use of AWS Lambda for running code without provisioning or managing servers, further reducing infrastructure overhead.

---

### Task Summary:

This project successfully consolidates the **design, configuration**, and **peering** of a cloud-based virtual network for Daydreams Travel Agency into a single document. The following sections are covered:

1. **Virtual Network Design**: 
   - Documented in **Section A**, the network design outlines how AWS services like EC2, S3, VPC, IAM, and CloudWatch are used to meet the agency's business needs. The topology is carefully planned to ensure scalability, security, and high availability for on-site and remote employees.
   
2. **Configuration of Virtual Network and Peering**: 
   - In **Section B**, the AWS resources are configured, including the setup of VPCs, security groups, and routing tables. Screenshots and CLI commands validate the proper configuration of EC2 instances, subnets, NAT gateways, and peering connections between VPCs. Testing ensures the smooth flow of network traffic.
   
3. **Peering Between VPCs**: 
   - **Section C** focuses on establishing and testing VPC peering connections, allowing traffic to flow between two isolated virtual networks using private IP addresses. Routing tables are updated to reflect the connections, and logs confirm secure inter-VPC communication.

The portfolio has been consolidated into a single document for ease of review, with all design details, configurations, screenshots, and testing results included. The plan successfully addresses Daydreams Travel Agency's goals of transitioning to a secure, cloud-based infrastructure, with provisions for scalability and future expansion.
---
**Sign-Off Requested From**:  
**Cloud Manager**
