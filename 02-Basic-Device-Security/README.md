# 🔐 Basic Device Security Lab

This lab demonstrates foundational device security practices using Cisco routers and switches, including password protection, hostname configuration, and encryption techniques.

---

## 🔍 Overview

In this lab, I configured hostnames, secure device access with passwords, enable encryption, and verify password storage security in Cisco IOS.

---

## 🧰 Devices Used

- 1 Router (`R1`)
- 1 Switch (`SW1`)

---

## 🔑 Security Configurations Made

| Task                                           | Configuration Details                            |
|------------------------------------------------|--------------------------------------------------|
| Hostname                                       | R1 and SW1                                       |
| Unencrypted Enable Password                    | `enable password CCNA`                           |
| View Password in Config                        | `show running-config` (before encryption)        |
| Enable Password Encryption                     | `service password-encryption`                    |
| Encrypted Enable Secret Password               | `enable secret Cisco`                            |
| Test Privileged Access                         | `enable` → Password: Cisco                       |
| View Password Types                            | Type 7 (`enable password`), Type 5 (`secret`)    |
| Save Configuration                             | `copy running-config startup-config`            |

---

## 🧪 What I Did

- Renamed devices with proper hostnames
- Set and tested both `enable password` and `enable secret`
- Enabled password encryption to secure existing/future passwords
- Observed how encrypted passwords appear in the running config
- Noted the encryption types:
  - Type 7: Weak (obfuscation)
  - Type 5: Strong (MD5 hash)
- Verified proper security behavior through CLI

---

## 💡 Takeaways

- I understood the difference between `enable password` vs `enable secret`
- I learned how to view and interpret encryption types in configs
- I reinforced why `enable secret` is the preferred secure method
- I practiced essential hardening steps for Cisco devices
- I gained insight into password visibility and encryption on IOS

---

## 🖥️ How to Open the Lab File

1. 🔽 **Download** the `.pkt` file from this folder  
   - Click the file  
   - Then click **“View Raw”** to save it to your machine  
2. 📂 **Open** it using **Cisco Packet Tracer** (version 8.0 or later recommended)

---

## 🛠️ Don’t Have Packet Tracer?

➡️ Download it for free via Cisco Networking Academy:  
https://www.netacad.com/portal/resources/packet-tracer  
*(Requires a free NetAcad account)*

Once opened, you can explore CLI configurations, test login behavior, and check your understanding of secure device access.

---

> 🧠 Lab created as part of my **CCNA self-study journey.**  
> Feel free to explore, copy, and practice!
