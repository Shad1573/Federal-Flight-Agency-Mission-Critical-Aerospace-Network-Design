# Federal Flight Agency Network Design

## 🚀 Project Overview
This project involves the design and implementation of a mission-critical, high-availability network for the **Federal Flight Agency**. The architecture supports a fully autonomous aircraft fleet, integrating real-time AI navigation, ground command stations, and emergency override systems. 

The network is engineered for **zero-point failure** through redundant paths and strict routing constraints.

## 🛠️ Key Features
- **VLSM Implementation:** Efficient IP addressing using Variable Length Subnet Masking based on a `1.0.0.0/16` base network.
- **Multi-Protocol Routing:** - **Dynamic:** RIPv2 for sub-unit communication with `no auto-summary` for precise pathing.
  - **Static:** Next-hop and Exit-interface routing for secure Command Center and Emergency Node links.
- **Redundancy:** A **Floating Static Route** (Administrative Distance: 63) ensures failover from the AI Unit to HQ via the Simulation Sandbox.
- **Security & Isolation:** - Passive interfaces and `distribute-lists` prevent sensitive HQ route leakage to the Maintenance Hangar.
  - Emergency Node isolation from dynamic routing protocols.
- **Centralized Services:** Integrated DNS, Web (HTTP), and Email (SMTP/POP3) services hosted at HQ.

## 📂 Repository Contents
- **Federal_Flight_Agency_Network.pka**: The complete Cisco Packet Tracer simulation file.
- **Federal_Flight_Agency_Network.docx**: Full documentation including:
  - **Topology Diagram:** Logical and physical network layout.
  - **VLSM Tree:** Detailed subnetting math for all 5 major units.
  - **IP Addressing Table:** Exact assignments for every router interface, PC, and printer.
  - **Cisco IOS CLI Configurations:** Raw commands for all routers and servers.

## 🏗️ Network Architecture
The network is divided into five specialized zones:
1. **Command Center (HQ):** The network core managing flight control and global services.
2. **AI Navigation Unit:** Handles ML Engine and Data Processing.
3. **Aircraft Simulation Lab:** Features a DHCP-enabled testing environment.
4. **Maintenance Hangar:** Diagnostic and repair zone with restricted routing access.
5. **Emergency Control Node:** A high-security, statically-routed backup core.

## 🚦 How to Run
1. Download and install **Cisco Packet Tracer 8.2.1**.
2. Open the `.pka` file provided in this repository.
3. To verify connectivity, open any PC web browser and navigate to `www.federalfgt.control`.
4. To test failover, manually shut down the primary link between the AI Unit and Sim Lab; traffic will automatically reroute through the Simulation Sandbox.


