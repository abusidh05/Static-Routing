# Static Routing Between Two Networks in Packet Tracer

## Project Description

This project demonstrates a simple static routing setup between two different networks using Cisco Packet Tracer. Two routers, Router A and Router B, are configured to enable communication between networks connected to their respective Fast Ethernet and Serial interfaces. A static routing configuration is used to establish the routes.

### Topology Overview
- **Router A**:
  - Fast Ethernet Interface: `10.0.0.1/8`
  - Serial Interface: `20.0.0.1/8`
- **Router B**:
  - Fast Ethernet Interface: `30.0.0.1/8`
  - Serial Interface: `20.0.0.2/8`

The static routes are configured to allow communication between the networks (`10.0.0.0/8` and `30.0.0.0/8`).

---

## Features
- Configuration of basic network settings (IP addresses, interfaces).
- Static routing for inter-network communication.
- Demonstrates the use of the `255.0.0.0` subnet mask.
- Simulation of data packet flow between networks.

---

## Prerequisites
To replicate this project, you need the following:
1. **Cisco Packet Tracer** installed on your system.
2. Basic understanding of networking concepts, including IP addressing and routing.

---

## Network Topology

The network setup consists of:
1. **Router A**:
   - Interface `FastEthernet0/0`: `10.0.0.1/8`
   - Interface `Serial0/0/0`: `20.0.0.1/8`
2. **Router B**:
   - Interface `Serial0/0/0`: `20.0.0.2/8`
   - Interface `FastEthernet0/0`: `30.0.0.1/8`

---

## Configuration Steps

### 1. Router A Configuration
  a. Assign IP addresses to the interfaces:
   ```bash
   RouterA> enable
   RouterA# configure terminal
   RouterA(config)# interface FastEthernet0/0
   RouterA(config-if)# ip address 10.0.0.1 255.0.0.0
   RouterA(config-if)# no shutdown
   RouterA(config-if)# exit
   RouterA(config)# interface Serial0/0/0
   RouterA(config-if)# ip address 20.0.0.1 255.0.0.0
   RouterA(config-if)# no shutdown
   RouterA(config-if)# exit
   ```
  b. Configure a static route to Router B's network:
   ```bash
   RouterA(config)# ip route 30.0.0.0 255.0.0.0 20.0.0.2
   ```
### 2. Router B Configuration
  a. Assign IP addresses to the interfaces:
   ```bash
    RouterB> enable
    RouterB# configure terminal
    RouterB(config)# interface FastEthernet0/0
    RouterB(config-if)# ip address 30.0.0.1 255.0.0.0
    RouterB(config-if)# no shutdown
    RouterB(config-if)# exit
    RouterB(config)# interface Serial0/0/0
    RouterB(config-if)# ip address 20.0.0.2 255.0.0.0
    RouterB(config-if)# no shutdown
    RouterB(config-if)# exit
   ```
  b. Configure a static route to Router A's network:
   ```bash
   RouterB(config)# ip route 10.0.0.0 255.0.0.0 20.0.0.1
   ```
### 3. Use the ping command from Router A to reach Router B's Fast Ethernet interface (30.0.0.1).
   ```bash
   RouterA# ping 30.0.0.1
   ```
### 4. Use the ping command from Router B to reach Router A's Fast Ethernet interface (10.0.0.1).
   ```bash
   RouterB# ping 10.0.0.1
   ```

## Screenshots
### 1. Network Topology Diagram
   ![image](https://github.com/user-attachments/assets/e5026339-bbb6-4276-8e23-7ea78bffe642)

### 2. Router A Configuration
   ![image](https://github.com/user-attachments/assets/015c1b3a-fe49-44d0-a261-e14ca1e4cd84)

### 3. Router B Configuration
   ![image](https://github.com/user-attachments/assets/163db7f2-5c87-4730-bde4-17a9b81e40aa)
   
---
## How to Replicate
1. Open Cisco Packet Tracer.
2. Create the topology as shown in the diagram.
3. Configure Router A and Router B using the commands provided above.
4. Verify connectivity using the ping command.

## Learning Outcomes
- Understanding static routing and its configuration.
- Familiarity with router interface setup in Cisco Packet Tracer.
- Insight into subnet masking and route configuration for inter-network communication.
---
## Author
- [LinkedIn Profile](https://www.linkedin.com/in/abusidh05/)
- [GitHub Profile](https://github.com/abusidh05)
