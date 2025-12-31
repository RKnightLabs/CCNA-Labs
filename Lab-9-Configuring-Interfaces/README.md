# 🛰️ Interface Configuration

## 📘 Overview

In this lab, I configure basic device settings, IP addressing, and interface parameters across a small routed network. The topology consists of one router and two switches providing connectivity to four end hosts within a single IPv4 network. The primary focus is on **hostname configuration**, **static IP addressing**, **manual speed and duplex settings**, **interface descriptions**, and **administrative shutdown of unused interfaces**.

---

## 🧪 Lab Tasks

### 🔍 1. Configure Device Hostnames

I configure meaningful hostnames on all networking devices to improve identification and management.

- Router: `R1`
- Switches: `SW1`, `SW2`

#### Expected Observations

- The CLI prompt updates to reflect the configured hostname on each device.
- Hostnames persist after saving the running configuration.

---

### 🧪 2. Configure IP Addressing

I manually configure IPv4 addresses on the router interface and all PCs using the provided addressing scheme.

- The router interface acts as the default gateway
- All end hosts are in the same IPv4 network

---

### 🔁 3. Configure Speed and Duplex

I manually configure **speed** and **duplex** on interfaces that connect to other networking devices (router-to-switch and switch-to-switch links).

- End-host interfaces are excluded
- Auto-negotiation is disabled where manual settings are applied

---

### 📊 4. Configure Interface Descriptions

I add descriptive labels to each active interface to clearly document what device or port it connects to.

- Improves troubleshooting
- Enhances configuration readability

---

### 🧹 5. Disable Unused Interfaces

I administratively shut down all switch interfaces that are not connected to any device.

- Reduces unnecessary broadcast traffic
- Improves security and follows best practices

---

## 🧰 Devices Used

- 1× Cisco 2911 Router  
- 2× Cisco 2960-24TT Switches  
- 4× PC-PT End Hosts  

---

## 🔌 Physical Connections

- R1 `G0/0` ↔ SW1 `G0/1`
- SW1 `G0/2` ↔ SW2 `G0/1`
- SW1 `F0/1` ↔ PC1
- SW1 `F0/2` ↔ PC2
- SW2 `F0/1` ↔ PC3
- SW2 `F0/2` ↔ PC4

---

## 🌐 IP Scheme

**Network:** `172.16.0.0/16`  
**Subnet Mask:** `255.255.0.0`

| Device | Interface | IP Address | Default Gateway |
|------|----------|------------|-----------------|
| R1 | G0/0 | 172.16.255.254 | N/A |
| PC1 | NIC | 172.16.0.1 | 172.16.255.254 |
| PC2 | NIC | 172.16.0.2 | 172.16.255.254 |
| PC3 | NIC | 172.16.0.3 | 172.16.255.254 |
| PC4 | NIC | 172.16.0.4 | 172.16.255.254 |

---

## 💡 Key Takeaways

- Hostnames improve device identification and operational clarity.
- Manual speed and duplex settings should only be applied to infrastructure links.
- Interface descriptions significantly enhance maintainability.
- Disabling unused interfaces is a foundational security best practice.
- Proper IP planning simplifies troubleshooting and verification.

---

## 🖥️ Useful Commands

```bash
hostname R1
hostname SW1
hostname SW2

interface g0/0
 ip address 172.16.255.254 255.255.0.0
 no shutdown
 description Link to SW1

interface g0/1
 speed 1000
 duplex full

show ip interface brief
show running-config
copy running-config startup-config

---

## 🖥️ How to Open the Lab File

I download the .pkt file from the repository.

I click View Raw to save it locally.

I open it with Cisco Packet Tracer 8.0 or later.

Need Packet Tracer?

Download from Cisco Networking Academy:
https://www.netacad.com/portal/resources/packet-tracer

Lab created as part of a CCNA self-study journey.
