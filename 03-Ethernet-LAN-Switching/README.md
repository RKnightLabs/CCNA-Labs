# 🔄 Ethernet LAN Switching Lab

This lab demonstrates MAC address learning and ARP behavior in a switched network with 4 PCs and 2 switches.

## 🔍 Overview
- Understand how switches learn MAC addresses dynamically  
- Observe ARP request and reply behavior in IPv4 networks  
- Practice clearing and verifying MAC address tables  
- Use Packet Tracer simulation mode to visualize traffic flow

## 🌐 Network Topology

- **Subnet:** 192.168.1.0/24  
- **PC IP Addresses:**  
  - PC1: 192.168.1.1 (connected to SW1, Fa0/1)  
  - PC2: 192.168.1.2 (connected to SW1, Fa0/2)  
  - PC3: 192.168.1.3 (connected to SW2, Fa0/1)  
  - PC4: 192.168.1.4 (connected to SW2, Fa0/2)  

- **Switch Connections:**  
  - SW1 to SW2: Point-to-point on Gig0/1 interfaces  

## 🔑 Lab Tasks

| Task                        | Description                                                                                      |
|-----------------------------|------------------------------------------------------------------------------------------------|
| 1. Ping Behavior Analysis   | PC1 pings PC3; identify messages sent and devices receiving them with empty MAC and ARP tables. |
| 2. Simulation Verification  | Use Packet Tracer’s Simulation Mode to observe frame flooding and traffic flow.                 |
| 3. MAC Address Learning     | Generate ping traffic between all PCs to populate MAC address tables on switches.              |
| 4. Verify MAC Address Tables| Use `show mac address-table` on both switches to confirm learned MAC addresses.                 |
| 5. Clear MAC Address Tables | Use `clear mac address-table dynamic` to clear learned MAC addresses on each switch.           |

## 🧪 Actions Taken
- Started with empty MAC address tables on both switches. I checked this using `show mac address-table` on privileged exec mode in each switch. 
- Sent ping from PC1 to PC3 and observed ARP requests broadcast and frame flooding on switches in simulation mode 
- Generated additional pings between PCs to populate MAC address tables  
- Verified MAC addresses learned on switches using `show mac address-table` command  
- Cleared MAC address tables using `clear mac address-table dynamic` command to observe effects on traffic  

## 💡 Key Takeaways
- Switches learn MAC addresses dynamically by inspecting source addresses of incoming frames  
- ARP requests are broadcast to all devices in the network to resolve IP to MAC addresses  
- Unknown destination MAC addresses cause switches to flood frames out all ports except source  
- As MAC tables populate, switches reduce flooding, improving network efficiency  
- Clearing MAC tables forces switches to relearn MAC addresses, temporarily increasing flooding  

## 💡 Expected Behavior

- ARP requests from PC1 will broadcast across the network, reaching all devices.  
- Switches flood unknown destination MAC frames out all ports except the source port.  
- Switches learn MAC addresses from frame source addresses and update their tables.  
- Subsequent pings reduce flooding as MAC address tables populate.

## 🖥️ Useful Commands

| Command                          | Purpose                                  |
|---------------------------------|------------------------------------------|
| `show mac address-table`         | Display MAC addresses learned by switch  |
| `clear mac address-table dynamic`| Clear dynamic MAC address entries         |

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
