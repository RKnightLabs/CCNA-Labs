# 🛰️ Static Routing Lab
This lab demonstrates the configuration of static routes across multiple routers to enable end-to-end communication between two PCs.

## 🔍 Overview
I learn to:
- Configure router interfaces and hostnames
- Assign proper IP addresses to all router interfaces and PCs
- Configure default gateways for end hosts
- Implement and verify static routing between routers

## 🌐 Network Topology
Four interconnected networks:
- **192.168.1.0/24** — PC1 network
- **192.168.12.0/24** — R1 to R2
- **192.168.13.0/24** — R2 to R3
- **192.168.3.0/24** — PC2 network

### 🧰 Devices Used
- 2 PCs: PC1 and PC2
- 2 Switches: SW1 and SW2
- 3 Routers: R1, R2, R3

## 🧾 IP Addressing & Interfaces
| Device | Interface | IP Address       | Notes                      |
|--------|-----------|------------------|----------------------------|
| PC1    | NIC       | 192.168.1.1      | Gateway: 192.168.1.254     |
| SW1    | F0/1      | -                | Connected to PC1           |
| SW1    | G0/1      | -                | Connected to R1            |
| R1     | G0/1      | 192.168.1.254    | Toward SW1/PC1             |
| R1     | G0/0      | 192.168.12.1     | Toward R2                  |
| R2     | G0/0      | 192.168.12.2     | Toward R1                  |
| R2     | G0/1      | 192.168.13.2     | Toward R3                  |
| R3     | G0/0      | 192.168.13.3     | Toward R2                  |
| R3     | G0/1      | 192.168.3.254    | Toward SW2/PC2             |
| SW2    | G0/1      | -                | Connected to R3            |
| SW2    | F0/1      | -                | Connected to PC2           |
| PC2    | NIC       | 192.168.3.1      | Gateway: 192.168.3.254     |

## ⚙️ Configuration Tasks
1. Configure **hostnames** and **IP addresses** on R1, R2, and R3 per topology.
2. Configure **PC1** with IP `192.168.1.1` and gateway `192.168.1.254`
3. Configure **PC2** with IP `192.168.3.1` and gateway `192.168.3.254`
4. On **R1**, **R2**, and **R3**, add static routes to reach all remote networks.

## 🔧 Actions Taken
- Assigned IPs and hostnames to routers and PCs
- Configured static routes on R1, R2, and R3
- Verified connectivity using `ping` from PC1 to PC2

## 🧠 Key Takeaways
- Static routing requires complete knowledge of the network paths
- Each router must have a route to all destination networks
- Proper interface descriptions and IP planning help reduce misconfiguration
- Verifying with `ping` ensures accurate path communication

## 🖥️ How to Access the Lab File
- Download the `.pkt` file from the shared folder
- Click “View Raw” to save the file locally
- Open using **Cisco Packet Tracer** (version 8.0 or later recommended)

## 🛠️ Need Packet Tracer?
- Download for free at Cisco Networking Academy:  
  [https://www.netacad.com/portal/resources/packet-tracer](https://www.netacad.com/portal/resources/packet-tracer)  
- Requires a free NetAcad account

## 🧠 Notes
This lab is part of my ongoing **CCNA self-study journey**.  
Feel free to explore, practice, and replicate the configurations.

---
Created By *[Ryan Knight]*
