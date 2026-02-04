# Dual-LAN Topology Configuration

## Overview
This lab demonstrates **Inter-Network Routing**. It uses a central router to bridge two separate Local Area Networks (LANs), allowing devices on different subnets to communicate.

## Topology Diagram
![Dual LAN Topology](.\DualLanTopology.png)

## Hardware Used
* **Router:** Cisco 2911
* **Switches:** Cisco 2950-24
* **Cabling:** Copper Straight-Through

## Addressing Table
| Device | Interface | IP Address | Subnet Mask | Default Gateway |
| :--- | :--- | :--- | :--- | :--- |
| **Router** | Gig0/0 | 192.168.10.1 | 255.255.255.0 | N/A |
| **Router** | Gig0/1 | 192.168.20.1 | 255.255.255.0 | N/A |
| **Laptop0** | Fa0 | 192.168.10.2 | 255.255.255.0 | 192.168.10.1 |
| **PC0** | Fa0 | 192.168.20.2 | 255.255.255.0 | 192.168.20.1 |

## Router Configuration (CLI)

The following commands were used to enable the interfaces and assign IP addresses:

```bash
Router> enable
Router# configure terminal
Enter configuration commands, one per line. End with CNTL/Z.

Router(config)# interface Gig0/0
Router(config-if)# ip address 192.168.10.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit

Router(config)# interface Gig0/1
Router(config-if)# ip address 192.168.20.1 255.255.255.0
Router(config-if)# no shutdown