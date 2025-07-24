# 🛠️ Troubleshooting Static Routes Lab

This lab challenges me to identify and correct routing misconfigurations in a multi-router network where end devices cannot communicate.

---

## 🔍 Overview

In this lab, I will troubleshoot static route configurations across three routers. misconfigurations in the static routing tables prevent PC1 and PC2 from successfully pinging each other.

I will:

- Analyze router configurations
- Identify static routing errors
- Correct one misconfiguration on each router
- Verify end-to-end connectivity

---

## 🧰 Devices Used

- 2 PCs
- 2 Switches
- 3 Routers

---

## 🌐 Network Topology

| Device        | Interface      | IP Address      | Connected To       |
|---------------|----------------|------------------|---------------------|
| **PC1**       | Fa0/1          | 192.168.1.1      | SW1                 |
| **SW1**       | -              | -                | PC1, R1             |
| **R1**        | G0/1           | 192.168.1.254    | SW1                 |
| **R1**        | G0/0           | 192.168.12.1     | R2 G0/0             |
| **R2**        | G0/0           | 192.168.12.2     | R1 G0/0             |
| **R2**        | G0/1           | 192.168.13.2     | R3 G0/0             |
| **R3**        | G0/0           | 192.168.13.3     | R2 G0/1             |
| **R3**        | G0/1           | 192.168.3.254    | SW2                 |
| **SW2**       | -              | -                | R3, PC2             |
| **PC2**       | Fa0/1          | 192.168.3.1      | SW2                 |

### 📡 Networks Used

- `192.168.1.0/24` – PC1 ↔ SW1 ↔ R1
- `192.168.12.0/24` – R1 ↔ R2
- `192.168.13.0/24` – R2 ↔ R3
- `192.168.3.0/24` – R3 ↔ SW2 ↔ PC2

---

## ⚠️ Problem Statement

> **PC1 and PC2 are unable to ping each other.**

Each router (R1, R2, R3) contains **one misconfigured static route** that prevents end-to-end communication.

---

## 🧪 Lab Tasks

1. **Access CLI of each router** (R1, R2, R3)
2. **Use `show ip route`** to inspect static routes
3. **Use `ping` and `traceroute`** to verify reachability step-by-step
4. **Identify and correct the misconfiguration** on:
   - R1
   - R2
   - R3
5. **Test connectivity** between PC1 and PC2

> ✅ You have successfully completed the lab when **PC1 can ping PC2** and vice versa.

---

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
*Created By [Ryan Knight]*
