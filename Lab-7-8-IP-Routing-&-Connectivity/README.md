# 🛰️ IPv4 Routing and Connectivity Lab

## 📘 Overview

In this lab, I configure a single router with multiple interfaces to provide connectivity between three separate IPv4 networks. I assign IP addresses, verify interface status, configure end devices, and validate end-to-end connectivity using ICMP. This lab reinforces foundational CCNA skills related to interface configuration, routing awareness, and troubleshooting.

---

## 🧪 Lab Tasks

### 🔍 1. Configure Router Identity and Interfaces

I begin by configuring R1’s hostname and reviewing available interfaces using IOS show commands. I then assign the appropriate IP address to each interface, apply interface descriptions, and enable them.

#### Expected Observations

* Router interfaces transition from administratively down to up/up
* Each interface reflects the correct IPv4 address and subnet mask
* Interface descriptions clearly identify connected networks

---

### 🧪 2. Verify Router Configuration

I verify the interface configuration using show commands to confirm operational status and correct addressing. I also review the running configuration to ensure all changes are present before saving.

---

### 🔁 3. Configure End Devices

I manually configure IPv4 addresses, subnet masks, and default gateways on PC1, PC2, and PC3 to match their respective networks and router interfaces.

---

### 📊 4. Test Network Connectivity

I test connectivity by sending ICMP echo requests between PCs located on different networks to confirm successful routing through R1.

---

### 🧹 5. Save and Document Configuration

I save the running configuration to NVRAM and review the final topology to confirm that all devices are correctly configured and operational.

---

## 🧰 Devices Used

* 1× Cisco 2911 Router (R1)
* 3× Cisco 2960-24TT Switches (SW1, SW2, SW3)
* 3× PCs (PC1, PC2, PC3)

---

## 🔌 Physical Connections

* PC1 → SW1 → R1 (G0/0)
* PC2 → SW2 → R1 (G0/1)
* PC3 → SW3 → R1 (G0/2)

---

## 🌐 IP Scheme

| Device | Interface | IP Address     | Subnet Mask   | Default Gateway |
| ------ | --------- | -------------- | ------------- | --------------- |
| PC1    | NIC       | 15.0.0.1       | 255.0.0.0     | 15.255.255.254  |
| R1     | G0/0      | 15.255.255.254 | 255.0.0.0     | N/A             |
| PC2    | NIC       | 182.98.0.1     | 255.255.0.0   | 182.98.255.254  |
| R1     | G0/1      | 182.98.255.254 | 255.255.0.0   | N/A             |
| PC3    | NIC       | 201.191.20.1   | 255.255.255.0 | 201.191.20.254  |
| R1     | G0/2      | 201.191.20.254 | 255.255.255.0 | N/A             |

---

## 🖼️ Topology Diagram

![Topology Diagram](./IPV4 Addresses.png)

---

## 💡 Key Takeaways

* A router provides Layer 3 connectivity between separate IPv4 networks
* Each router interface represents a unique broadcast domain
* Proper IP addressing and default gateway configuration are critical for end-to-end communication
* Show commands are essential for verification and troubleshooting

---

## 🖥️ Useful Commands

```
show ip interface brief
show interfaces
show running-config
copy running-config startup-config
ping
```

---

## 🖥️ How to Open the Lab File

1. I download the `.pkt` file from the repository.
2. I click “View Raw” to save it locally.
3. I open it with **Cisco Packet Tracer 8.0 or later**.

### Need Packet Tracer?

Download from Cisco Networking Academy:
[https://www.netacad.com/portal/resources/packet-tracer](https://www.netacad.com/portal/resources/packet-tracer)

---

*Lab created as part of a CCNA self-study journey.*
