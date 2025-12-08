# 🛰️ Analyzing OSI Traffic

## 📘 Overview

This lab focuses on analyzing network traffic using Cisco Packet Tracer’s **Simulation Mode**. You will observe OSI layers in action and generate Layer 7 traffic by releasing and renewing an IP address on PC1.

---

## 🧪 Lab Tasks

### 🔍 1. Analyze Traffic Using Simulation Mode

Use **Simulation Mode** to watch packet flow throughout the network. Observe:

* Which protocols are triggered
* The OSI layers involved
* How packets move between routers, switches, and end devices

#### Expected Observations

Common traffic will show:

* **Layer 2:** Ethernet frames
* **Layer 3:** IP packets
* **Layer 4:** TCP/UDP segments
* **Layer 7:** Application protocols (DHCP, DNS, HTTP, etc.)

---

### 📡 2. Generate Layer 7 Traffic (DHCP Release/Renew) (DHCP Release/Renew)

Use PC1 to force DHCP communication.

**Commands:**

```
ipconfig /release
ipconfig /renew
```

#### What Happens

This triggers the DHCP process:

* DHCP Discover
* DHCP Offer
* DHCP Request
* DHCP ACK

In Simulation Mode you will see:

* Layer 2 broadcasts
* Layer 3 addressing operations
* Layer 4 UDP ports 67/68
* Layer 7 DHCP messages

---

## 🧰 Devices Used

* 1 PC (PC1)
* 2 Switches (SW1, SW2)
* 2 Routers (R1, R2)
* 1 Server (SRV1)

---

## 🔌 Connections Made

* PC1 → SW2 (F0/1): Straight-Through
* SW2 → SW1 (G0/1 ↔ G0/1): Crossover
* SW1 → SRV1 (F0/1): Straight-Through
* SW1 → R1 (G0/2 → G0/0): Straight-Through
* R1 → R2 (G0/1 → G0/0): Straight-Through

---

## 🌐 IP Scheme

* **Server SRV1:** 192.168.1.100/24 (Gateway: 192.168.1.1)
* **R1 G0/0:** 192.168.1.1/24
* **R1 G0/1:** 10.0.0.1/24
* **R2 G0/0:** 10.0.0.2/24
* **PC1:** DHCP (assigned 192.168.1.x from SRV1)

---

## 💡 Takeaways

* Simulation Mode helps visualize real packet behavior across OSI layers.
* DHCP renewals are a useful method for generating Layer 7 traffic.
* Understanding physical cabling improves network troubleshooting and analysis.

---

## 🖥️ How to Open the Lab File

1. Download the `.pkt` file from the repository.
2. Open it in **Cisco Packet Tracer** (version 8.0 or later recommended).
3. To get Packet Tracer:

   * [https://www.netacad.com/portal/resources/packet-tracer](https://www.netacad.com/portal/resources/packet-tracer)

Once open, switch to **Simulation Mode** and observe the traffic flow.

---

*Lab created as part of a CCNA self-study journey.*
