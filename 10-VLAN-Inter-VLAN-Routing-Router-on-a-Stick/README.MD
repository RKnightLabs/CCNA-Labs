# 🧪 CCNA Lab: VLAN Inter-VLAN Routing with Router-on-a-Stick

## 🔍 Overview
This lab demonstrates VLAN segmentation, trunking, and inter-VLAN routing using a single router-on-a-stick configuration.  
The goal is to configure VLANs, trunk links, and router subinterfaces so that devices in different VLANs can communicate.

---

### 📡 Devices Used
- **7 PCs**
- **2 Switches (SW1, SW2)**
- **1 Router (R1)**

### 🧩 Network Layout

| VLAN  | Subnet           | Gateway IP       | Devices & IPs                                        |
|-------|------------------|------------------|------------------------------------------------------|
| 10    | 10.0.0.0/26      | 10.0.0.62         | PC1: 10.0.0.1, PC2: 10.0.0.2, PC6: 10.0.0.4, PC7: 10.0.0.3 |
| 20    | 10.0.0.64/26     | 10.0.0.126        | PC5: 10.0.0.65                                       |
| 30    | 10.0.0.128/26    | 10.0.0.190        | PC3: 10.0.0.129, PC4: 10.0.0.130                     |

---

## 🔌 Physical Connections

| Device | Interface | Connected To | Interface |
|--------|-----------|--------------|-----------|
| PC1    | Fa0/1     | SW1          | Fa0/1     |
| PC2    | Fa0/2     | SW1          | Fa0/2     |
| PC3    | Fa0/3     | SW1          | Fa0/3     |
| PC4    | Fa0/4     | SW1          | Fa0/4     |
| SW1    | Gi0/1     | SW2          | Gi0/1     |
| PC5    | Fa0/1     | SW2          | Fa0/1     |
| PC6    | Fa0/2     | SW2          | Fa0/2     |
| PC7    | Fa0/3     | SW2          | Fa0/3     |
| SW2    | Gi0/2     | R1           | Gi0/0     |

---

### 🖥️ PC Configuration
I assigned each PC its respective IP address, subnet mask, and default gateway based on the VLAN subnet.

---

### 🖥️ Switch Configuration
1. ** I Assigned VLANs and configured access ports**  
   - VLAN 10: Fa0/1, Fa0/2 (SW1) and Fa0/2, Fa0/3 (SW2)  
   - VLAN 20: Fa0/1 (SW2)  
   - VLAN 30: Fa0/3, Fa0/4 (SW1)  

2. **I Created VLANs on both switches**  
vlan 10
vlan 20
vlan 30
vlan 1001 ← Native VLAN

3. **I Configured trunk link between SW1 and SW2**  
- Allow only VLANs 10, 20, 30  
- Set VLAN 1001 as native  

---

### Router Configuration (Router-on-a-Stick)
1. Configure subinterfaces on **R1**:
interface g0/0.10
encapsulation dot1q 10
ip address 10.0.0.62 255.255.255.192
interface g0/0.20
encapsulation dot1q 20
ip address 10.0.0.126 255.255.255.192
interface g0/0.30
encapsulation dot1q 30
ip address 10.0.0.190 255.255.255.192

---

## 🔄 Lab Tasks
1. Configure the switch interfaces connected to PCs as access ports in the correct VLAN.
2. Configure the trunk between SW1 and SW2, allowing only the necessary VLANs, and set VLAN 1001 as native.
3. Create all necessary VLANs on both switches.
4. Configure router-on-a-stick on R1 using the last usable IP in each subnet.
5. Test connectivity between all PCs.

---

## ✅ Actions Taken
- VLANs created on both switches  
- Access ports assigned to correct VLANs  
- Trunk link between SW1 and SW2 configured with VLAN 1001 as native  
- Router subinterfaces configured with proper encapsulation and IPs  
- PCs configured with IP, mask, and gateway  

---

## 💡 Expected Behavior
- All PCs can ping each other across VLANs via R1.
- VLAN segmentation remains intact for broadcast domains.

---

## 🔑 Key Takeaways
- VLANs segment networks at Layer 2, but require Layer 3 routing to communicate.  
- Trunking allows VLAN traffic to traverse between switches on a single link.  
- Router-on-a-stick enables inter-VLAN routing with a single physical router interface.

---

## 🖥️ Useful Commands
show vlan brief
show interfaces trunk
ping <ip>
show running-config

---

## 🖥️ How to Access the Lab File
- Download the `.pkt` file from the shared folder
- Click “View Raw” to save the file locally
- Open using **Cisco Packet Tracer** (version 8.0 or later recommended)

## 🛠️ Need Packet Tracer?
- Download for free at Cisco Networking Academy:  
  [https://www.netacad.com/portal/resources/packet-tracer](https://www.netacad.com/portal/resources/packet-tracer)  
- Requires a free NetAcad account

---

## 🧠 Notes
This lab is part of my ongoing **CCNA self-study journey**.  
Feel free to explore, practice, and replicate the configurations.

---

Created By *Ryan Knight*
