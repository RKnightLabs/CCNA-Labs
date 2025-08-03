# 🧪 CCNA Lab: VLAN Routing with Subnet Gateways

## 🧠 Objective
To configure inter-VLAN routing setup and verify connectivity between VLANs in a segmented network.

---

## 🖥️ Topology Overview

### 📡 Devices Used
- 6 PCs
- 1 Switch (SW1)
- 1 Router (R1)

### 🧩 Network Layout

| VLAN | Department  | Subnet            | Range             | Gateway       | PCs (IP)          |
|------|-------------|-------------------|-------------------|---------------|-------------------|
| 10   | Engineering | 10.0.0.0/26       | .1 – .62          | 10.0.0.62     | PC1 (.1), PC2 (.2) |
| 20   | HR          | 10.0.0.64/26      | .65 – .126        | 10.0.0.126    | PC3 (.65), PC4 (.66) |
| 30   | Sales       | 10.0.0.128/26     | .129 – .190       | 10.0.0.190    | PC5 (.129), PC6 (.130) |

---

## 🔌 Physical Connections

| Device     | Interface | Connected To     | Interface | Notes               |
|------------|-----------|------------------|-----------|---------------------|
| PC1        | NIC       | SW1              | Fa3/1     | VLAN 10             |
| PC2        | NIC       | SW1              | Fa4/1     | VLAN 10             |
| PC3        | NIC       | SW1              | Fa5/1     | VLAN 20             |
| PC4        | NIC       | SW1              | Fa6/1     | VLAN 20             |
| PC5        | NIC       | SW1              | Fa7/1     | VLAN 30             |
| PC6        | NIC       | SW1              | Fa8/1     | VLAN 30             |
| SW1        | G0/1      | R1               | G0/0      | VLAN 10 Gateway     |
| SW1        | G1/1      | R1               | G0/1      | VLAN 20 Gateway     |
| SW1        | G2/1      | R1               | G0/2      | VLAN 30 Gateway     |

---

## ⚙️ Configuration Steps

### 🖥️ PC Configuration
Each PC is manually assigned:
- **IP Address:** As listed above
- **Subnet Mask:** 255.255.255.192 (/26)
- **Default Gateway:** Last usable address in each subnet

---

## ✅ Expected Results
PCs within the same VLAN can reach each other
PCs from one VLAN can ping PCs in the other VLANs via router
Broadcast pings stay within their VLAN scope
MAC tables correctly reflect dynamic learning

📎 Notes
Verify  configuration on the switch interfaces going to the router.
Ensure correct default gateways are configured on PCs.
Use Simulation Mode in Packet Tracer to see ARP requests/replies and pings.

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


