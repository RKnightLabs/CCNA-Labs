# 🧠 CCNA Subnetting and Static Routing Lab

Welcome to my CCNA lab! This project is part of my journey to mastering fundamental networking concepts. In this lab, I designed and configured a network topology using subnetting, point-to-point routing, and static routing to allow full communication between multiple LANs.

## 🧾 Lab Objective

The goal of this lab is to:

- Subnet a single `/24` network into multiple subnets
- Assign IP addresses according to host requirements
- Configure end devices and routers using Cisco IOS
- Establish static routing so all devices can communicate
- Solidify subnetting and routing knowledge using real-world practice

## 🌐 Topology Overview

csharp
Copy
Edit
              [PC1]
                |
              [SW1]
                |
     LAN1 --> R1 G0/0
              R1 G0/1 <-- LAN2
                |           |
              [SW2]       [PC2]
                              
     R1 G0/0/0 <--> G0/0/0 R2  (Point-to-Point)
      
       R2 G0/0 --> LAN3
                |      \
              [SW3]   [PC3]

       R2 G0/1 --> LAN4
                |      \
              [SW4]   [PC4]
nginx
Copy
Edit

## 🧮 Subnetting Requirements

Original Network: `192.168.5.0/24`  
I used VLSM (Variable Length Subnet Masking) to meet the host requirements efficiently:

| Subnet | Purpose         | Hosts Needed | Subnet Mask     | Address Range            | First Usable IP | Last Usable IP | Broadcast Address |
|--------|------------------|--------------|------------------|---------------------------|------------------|-----------------|--------------------|
| LAN2   | Largest LAN      | 64           | /25 (255.255.255.128) | 192.168.5.0 - 192.168.5.127 | 192.168.5.1     | 192.168.5.126   | 192.168.5.127     |
| LAN1   | Medium LAN       | 45           | /26 (255.255.255.192) | 192.168.5.128 - 192.168.5.191 | 192.168.5.129   | 192.168.5.190   | 192.168.5.191     |
| LAN3   | Small LAN        | 14           | /28 (255.255.255.240) | 192.168.5.192 - 192.168.5.207 | 192.168.5.193   | 192.168.5.206   | 192.168.5.207     |
| LAN4   | Tiny LAN         | 9            | /28 (255.255.255.240) | 192.168.5.208 - 192.168.5.223 | 192.168.5.209   | 192.168.5.222   | 192.168.5.223     |
| P2P    | R1 <--> R2 Link  | 2            | /30 (255.255.255.252) | 192.168.5.224 - 192.168.5.227 | 192.168.5.225   | 192.168.5.226   | 192.168.5.227     |

## 💻 IP Address Assignments

| Device | Interface | Assigned IP        |
|--------|-----------|--------------------|
| PC1    | NIC       | 192.168.5.129      |
| R1     | G0/0      | 192.168.5.190      |
| PC2    | NIC       | 192.168.5.1        |
| R1     | G0/1      | 192.168.5.126      |
| R1     | G0/0/0    | 192.168.5.225      |
| R2     | G0/0/0    | 192.168.5.226      |
| PC3    | NIC       | 192.168.5.193      |
| R2     | G0/0      | 192.168.5.206      |
| PC4    | NIC       | 192.168.5.209      |
| R2     | G0/1      | 192.168.5.222      |

## ⚙️ Configuration Steps

### 1. Configure Interfaces

Each router and PC was manually assigned an IP from the appropriate subnet. Descriptions and `no shutdown` commands were used to activate the interfaces.

### 2. Static Routing

To ensure end-to-end connectivity, I added static routes on both routers.

#### On R1:
```bash
ip route 192.168.5.192 255.255.255.240 192.168.5.226  ! LAN3
ip route 192.168.5.208 255.255.255.240 192.168.5.226  ! LAN4
On R2:
bash
Copy
Edit
ip route 192.168.5.0   255.255.255.128 192.168.5.225  ! LAN2
ip route 192.168.5.128 255.255.255.192 192.168.5.225  ! LAN1
🧪 Testing & Validation
Verified each interface using show ip interface brief

Tested connectivity with ping from PC1 to PC2, PC3, and PC4
Confirmed routing table entries with show ip route
Ensured no packet loss across the topology

🧰 Tools Used
Cisco Packet Tracer
CLI configuration via routers and switches
Subnetting calculations by hand

✅ What I Learned
How to subnet efficiently using VLSM
Assigning usable IPs based on specific host needs
Static route configuration and testing
Topology design and interface documentation

🖥️ How to Access the Lab File
Download the .pkt file from the shared folder
Click “View Raw” to save the file locally
Open using Cisco Packet Tracer (version 8.0 or later recommended)
🛠️ Need Packet Tracer?
Download for free at Cisco Networking Academy:
https://www.netacad.com/portal/resources/packet-tracer
Requires a free NetAcad account
🧠 Notes
This lab is part of my ongoing CCNA self-study journey.
Feel free to explore, practice, and replicate the configurations.

Created By [Ryan Knight]
