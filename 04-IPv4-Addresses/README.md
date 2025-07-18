# 🔄 Basic Router and Switch Configuration Lab

This lab demonstrates configuring a router (R1) with multiple interfaces and connecting PCs through switches across different subnets. 
It covers interface configuration, IP addressing, verification, and basic connectivity testing.

---

## 🔍 Overview

- Configure router hostname and interface IPs  
- Understand enabling interfaces and setting descriptions  
- Verify interface statuses using show commands  
- Configure PCs with IP addresses matching router subnets  
- Test end-to-end connectivity using ping commands  

---

## 🌐 Network Topology

| Device | Connection           | Interface          | Network           | IP Address          |
|--------|----------------------|--------------------|-------------------|---------------------|
| PC1    | Connected to SW1     | F0/0               | 15.0.0.0/8        | 15.0.0.1            |
| SW1    | Connected to R1      | G0/1               |                   |                     |
| R1     | Connected to SW1     | G0/0               | 15.0.0.0/8        | 15.255.255.254      |
| PC2    | Connected to SW2     | F0/0               | 182.98.0.0/16     | 182.98.0.1          |
| SW2    | Connected to R1      | G0/1               |                   |                     |
| R1     | Connected to SW2     | GigabitEthernet0/1 | 182.98.0.0/16     | 182.98.255.254      |
| PC3    | Connected to SW3     | F0/0               | 201.191.20.0/24   | 201.191.20.1        |
| SW3    | Connected to R1      | G0/1               |                   |                     |
| R1     | Connected to SW3     | G0/2               | 201.191.20.0/24   | 201.191.20.254      |

---

## 🔑 Lab Tasks

| Task                     | Description                                                  |
|--------------------------|--------------------------------------------------------------|
| 1. Configure Hostname    | Set router hostname to "R1"                                  |
| 2. Show Interfaces       | Use `show ip interface brief` to verify interface status    |
| 3. Configure Interfaces  | Assign IP addresses and enable interfaces with descriptions |
| 4. Verify Configuration  | Re-run show commands to verify changes                       |
| 5. Save Configuration    | Save running config to startup config                        |
| 6. Configure PCs         | Set IPs, subnet masks, and gateways on PC1, PC2, and PC3    |
| 7. Test Connectivity     | Ping from PC1 to PC2 and PC3 to ensure network reachability |

---

## 🧪 Actions Taken

- Configured router hostname to R1  
- Viewed interface status using show commands  
- Set IP addresses and interface descriptions on R1  
- Enabled all router interfaces  
- Verified interfaces are up and configured properly  
- Saved configuration to prevent loss after reboot  
- Configured PC IP addresses matching each subnet  
- Tested connectivity with ping commands to verify communication  

---

## 💡 Key Takeaways

- Proper interface configuration is critical for inter-network communication  
- Interface descriptions improve network documentation  
- `show` commands are essential for verifying device status and troubleshooting  
- Saving configuration preserves changes across device reloads  
- Testing with ping verifies successful network setup and connectivity  

---

## 🖥️ Useful Commands

| Command                      | Purpose                                         |
|------------------------------|------------------------------------------------|
| `show ip interface brief`    | Displays brief summary of interface status and IP addresses |
| `show running-config`        | Views the current configuration in RAM         |
| `copy running-config startup-config` | Saves running config to NVRAM (persists on reboot) |
| `ping [IP address]`          | Tests reachability to another device            |

---

## 🖥️ How to Access the Lab File

- Download the Packet Tracer file: `BasicRouterLab.pkt`  
- Open using Cisco Packet Tracer (version 8.0 or later recommended)  

---

## 🛠️ Need Packet Tracer?

Download for free at Cisco Networking Academy:  
https://www.netacad.com/portal/resources/packet-tracer  
Requires a free NetAcad account.

---

## 🧠 Notes

This lab is part of my CCNA self-study journey focused on router and switch configuration fundamentals.

---

*Created by [Ryan Knight]*  
