# Peer to Peer Communication

## Overview
This lab demonstrates Peer to Peer communication between PC and a laptop.

## Topology Diagram
![Network Diagram](./PeerToPeer_topology.png)


## IP Configuration
| Device | Interface | IP Address | Subnet Mask |
| :--- | :--- | :--- | :--- |
| **PC0** | FastEthernet0 | 192.168.1.2 | 255.255.255.0 |
| **Laptop0** | FastEthernet0 | 192.168.1.3 | 255.255.255.0 |

## Testing
1. Open the **Command Prompt** on PC0.
2. Run the command: `ping 192.168.1.3`.
3. A successful reply confirms the P2P link is active.

## Alternatively
1. Open the **Command Prompt** on Laptop0.
2. Run the command: `ping 192.168.1.2`.
3. A successful reply confirms the P2P link is active.