# 🛰️ Ethernet LAN Switching

## 📘 Overview

This lab focuses on analyzing Ethernet LAN switching behavior, MAC address learning, ARP processes, and initial unknown-unicast forwarding. Using Cisco Packet Tracer’s **Simulation Mode**, I observe Layer 2 and Layer 3 operations as traffic moves between PCs across two interconnected switches.

---

## 🧪 Lab Tasks

### 🔍 1. Predict Initial Traffic Behavior

When PC1 pings PC3 while all switches have **empty MAC tables** and all PCs have **empty ARP tables**, I determine:

* What messages are generated
* Which devices receive the messages
* How switches forward unknown traffic

#### Expected Observations

* **ARP Request:** Broadcast by PC1 to discover PC3’s MAC
* **Switch Flooding:** Both SW1 and SW2 flood frames out all ports except the arrival port
* **ARP Reply:** PC3 responds unicast back to PC1
* **MAC Learning:** Switches learn source MACs for forwarding

---

### 🧪 2. Use Simulation Mode to Verify Traffic Flow

Utilize **Simulation Mode** to step through ARP Request, ARP Reply, and ICMP Echo/Reply messages.
I observe:

* Layer 2 Ethernet frame behavior
* ARP broadcasts and unicast replies
* Switch MAC address table population

---

### 🔁 3. Generate Additional Network Traffic

Send pings between all PCs:

* PC1 → PC4
* PC2 → PC3
* PC3 → PC1
* PC4 → PC2

This enables full MAC address learning across all interfaces for my lab.

---

### 📊 4. View MAC Address Tables

Use the following switch commands:

```
show mac address-table dynamic
```

I confirm:

* Each PC MAC is present
* Each MAC is mapped to the correct switch port

---

### 🧹 5. Clear the MAC Address Tables

```
clear mac address-table dynamic
```

Then I verify the tables are empty:

```
show mac address-table
```

---

## 🧰 Devices Used

* 4 PCs (PC1–PC4)
* 2 Switches (SW1, SW2)

---

## 🔌 Physical Connections

| From | Interface | To  | Interface |
| ---- | --------- | --- | --------- |
| PC1  | F0        | SW1 | F0/1      |
| PC2  | F0        | SW1 | F0/2      |
| SW1  | G0/1      | SW2 | G0/1      |
| PC3  | F0        | SW2 | F0/1      |
| PC4  | F0        | SW2 | F0/2      |

---

## 🌐 IP Scheme

* **PC1:** 192.168.1.1/24
* **PC2:** 192.168.1.2/24
* **PC3:** 192.168.1.3/24
* **PC4:** 192.168.1.4/24

---

## 🖼️ Topology Diagram

![Topology](Lab-6-Ethernet-LAN-Switching.png)

---

## 💡 Key Takeaways

* I observe that Layer 2 switches flood unknown unicast and broadcast frames
* ARP is required for initial IP communication
* MAC address tables populate dynamically based on source MACs
* Simulation Mode helps me visualize frame forwarding

---

## 🖥️ Useful Commands

### Switch Commands

```
show mac address-table
show mac address-table dynamic
clear mac address-table dynamic
show interfaces status
```

### PC Commands

```
arp -a
ping <ip>
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
