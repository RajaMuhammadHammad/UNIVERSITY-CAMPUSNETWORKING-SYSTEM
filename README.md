# University Campus Networking System

## Overview

The **University Campus Networking System** project provides a secure, scalable, and efficient network solution for university campuses with multiple departments. The network architecture uses Cisco Packet Tracer to design and configure a robust topology with VLANs, dynamic and static routing, and DHCP for IP address allocation. This system ensures traffic isolation between departments, secure communication, and seamless connectivity to external services like cloud-hosted email servers.

## Key Features

- **VLAN-Based Segmentation:** Network traffic is segmented based on departmental needs (Faculty, Labs, etc.) to ensure security and efficient communication.
- **Dynamic Routing (RIPv2):** RIPv2 is implemented for dynamic routing between departments, ensuring smooth data transfer within the internal network.
- **Static Routing:** Static routing is configured to connect the internal network to external services such as a cloud-hosted email server.
- **DHCP Configuration:** A DHCP server automatically assigns IP addresses to devices within each department, reducing manual configuration efforts.
- **Security:** VLAN security and Access Control Lists (ACLs) ensure that only authorized users can access specific network resources.

## Installation

To view and test the project, follow these steps:

### Prerequisites

- Cisco Packet Tracer (for simulation)
- Basic understanding of networking concepts like VLANs, RIPv2, DHCP, and Static Routing

### Setup Instructions

1. **Clone the repository:**
   ```bash
   git clone https://github.com/RajaMuhammadHammad/UNIVERSITY-CAMPUSNETWORKING-SYSTEM.git
   ```

2. **Open Cisco Packet Tracer:**
   - Open the `.pkt` file from the `PacketTracer` folder in Cisco Packet Tracer.

3. **Explore the Network Configuration:**
   - Inspect the configurations for routers, switches, and other devices.
   - Review the command-line interface (CLI) configurations for VLANs, RIPv2, Static Routing, and DHCP.

### Configuration Commands

Below are some of the key configuration commands used in the project:

- **VLAN Configuration on Switches:**
  ```bash
  en
  config t
  vlan 10
  name Faculty
  vlan 20
  name Labs
  exit
  int range f0/1 - 12
  switchport mode access
  switchport access vlan 10
  exit
  ```

- **RIPv2 Configuration on Routers:**
  ```bash
  router rip
  network 192.168.1.0
  network 192.168.2.0
  no auto-summary
  exit
  ```

- **Static Routing for External Server:**
  ```bash
  ip route 0.0.0.0 0.0.0.0 203.0.113.1
  ```

- **DHCP Configuration on Router:**
  ```bash
  en
  config t
  ip dhcp pool FacultyPool
  network 192.168.10.0 255.255.255.0
  default-router 192.168.10.1
  dns-server 8.8.8.8
  exit
  ```

## Project Structure

- `PacketTracer/`: Contains the Cisco Packet Tracer file for the network topology.
- `Docs/`: Includes project documentation and configuration details.
- `Images/`: Screenshots and diagrams of the network topology.
- `README.md`: Project description and setup instructions.

## Conclusion

This project successfully implements a secure, scalable network topology for a university campus, addressing departmental communication needs and ensuring security through VLANs, dynamic routing, and static routing. The network also provides seamless integration with external services through static routing and cloud connectivity.
