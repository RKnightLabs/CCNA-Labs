# 🔌 Interface Configuration Lab

This lab focuses on interface-level configuration including hostnames, IP addressing, speed/duplex settings, interface descriptions, and port security via unused port shutdowns. The network includes 1 router, 2 switches, and 4 PCs.

---

## 🧰 Devices Used

- 1 Router (R1)
- 2 Switches (SW1, SW2)
- 4 PCs (PC1–PC4)

---

## 🖧 Topology Overview

- **Network:** 172.16.0.0/16  
- **Router Interface:**  
  - R1 G0/0 → 172.16.255.254 → connected to SW1 G0/1  
- **Switch 1:**  
  - SW1 F0/1 → PC1 → 172.16.0.1  
  - SW1 F0/2 → PC2 → 172.16.0.2  
  - SW1 G0/2 → SW2 G0/1  
- **Switch 2:**  
  - SW2 F0/1 → PC3 → 172.16.0.3  
  - SW2 F0/2 → PC4 → 172.16.0.4  

---

## 🔧 Lab Tasks

| Task # | Description |
|--------|-------------|
| 1 | Configure the hostname of **R1**, **SW1**, and **SW2** |
| 2 | Assign the appropriate IP addresses to **R1**, **PC1**, **PC2**, **PC3**, and **PC4** |
| 3 | Manually configure **speed and duplex** on interfaces connected to networking devices (not end hosts) |
| 4 | Add **interface descriptions** for all connections |
| 5 | **Disable unused interfaces** on all network devices for security and stability |

---

## ⚙️ Actions Taken

- I set hostnames for R1, SW1, and SW2
- I assigned static IP addresses to PCs and router interface
- I used `speed` and `duplex` commands on uplinks and trunk ports
- I applied `description` commands for all connected interfaces
- I disabled unused switch ports using `shutdown`

---

## 💡 Key Takeaways

- Interface configuration is foundational for device communication
- Clear hostnames and descriptions reduce operational errors
- Manual speed/duplex settings improve stability on switch-router links
- Disabling unused ports is a best-practice security step
- These skills are essential for troubleshooting and securing enterprise networks

---

## 🖥️ How to Access the Lab File

- Download the `.pkt` file from the shared folder
- Click **“View Raw”** to save it to your computer
- Open using **Cisco Packet Tracer** (version 8.0 or later recommended)

---

## 🛠️ Need Packet Tracer?

Download for free at Cisco Networking Academy:  
[https://www.netacad.com/portal/resources/packet-tracer](https://www.netacad.com/portal/resources/packet-tracer)  
*Requires a free NetAcad account*

---

## 🧠 Notes

This lab is part of my ongoing **CCNA self-study journey**.  
Feel free to explore, replicate, and expand upon the setup for additional learning.

---

*Created By [Ryan Knight]*
