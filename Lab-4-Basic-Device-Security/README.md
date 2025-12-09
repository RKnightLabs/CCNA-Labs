🧪 Basic Device Security Lab
🔍 Overview

This lab demonstrates my ability to secure Cisco IOS devices, analyze password behavior, and apply best practices for device hardening.
I performed password configuration, encryption validation, and privilege-level testing on a router and switch while observing how IOS stores and protects credentials.

🌐 Topology Overview
<img src="Lab-4- Basic Device Security topology.png" width="600">
Devices Used

🖥️ PC1

🖥️ PC2

🖥️ PC3

🔀 Switch SW1 (2960)

📡 Router R1 (2911)

🔌 Physical Connections
Device	Connection
R1	Connected to SW1
SW1	Connected to PC1, PC2, PC3
⚙️ Configuration Steps Performed
1️⃣ Renamed Both Devices

Updated hostnames for clarity:

hostname R1
hostname SW1

2️⃣ Configured an Unencrypted Enable Password

I set an initial unencrypted enable password:

enable password CCNA


This allowed me to observe how IOS stores weak passwords.

3️⃣ Tested Password Behavior

Exited to user EXEC mode and confirmed that the device required “CCNA” to enter privileged EXEC mode.

4️⃣ Viewed Password in Running Config

Using:

show running-config


I confirmed that the password appeared in plain text, demonstrating insecure configuration.

5️⃣ Enabled Global Password Encryption

Applied encryption to all existing and future passwords:

service password-encryption


This converts all clear-text passwords into Type 7 encrypted strings.

6️⃣ Verified Encrypted Password

Re-viewed the running config to confirm that the “CCNA” password was now shown as Type 7 encrypted.

7️⃣ Configured a Secure Enable Secret

Added a stronger, hashed secret:

enable secret Cisco


Cisco IOS automatically applies Type 5 MD5 hashing — more secure than Type 7.

8️⃣ Tested Privileged EXEC Access Again

After exiting to user EXEC mode:

“CCNA” no longer worked

“Cisco” (the enable secret) was required

This confirms IOS privilege rules:
➡️ Enable secret overrides enable password

9️⃣ Verified Encryption Types

Using show run, I compared both password types:

Password Type	Encryption Style	Type #
enable password	Weak reversible encryption	Type 7
enable secret	MD5 hash	Type 5
🔟 Saved All Configurations

Saved work to NVRAM:

copy running-config startup-config


or

write memory

🔄 Lab Tasks Completed

✔️ Hostname configuration

✔️ Setup of unencrypted and encrypted passwords

✔️ Application of global encryption

✔️ Observation of Type 7 vs Type 5 behavior

✔️ Privilege EXEC testing

✔️ Final config saved successfully

💡 Expected Behavior

Unencrypted passwords appear in plain text

service password-encryption converts them to Type 7

enable secret uses Type 5 and overrides all other enable passwords

🧠 Key Takeaways

Type 7 passwords are weak and reversible

Type 5 provides significantly stronger protection

“Enable secret” should always replace “enable password”

Password behavior should always be tested after configuration

Reviewing the running config is essential to validate security posture

🖥️ Useful Commands
show running-config
enable password <password>
enable secret <password>
service password-encryption
hostname <name>
copy run start
exit

🖥️ How to Open the Lab File

🔽 Download the .pkt file from this folder

Click the file

Then click “View Raw” to save it to your machine

📂 Open it using Cisco Packet Tracer (version 8.0 or later recommended)

🛠️ Don’t Have Packet Tracer?

➡️ Download it for free from Cisco Networking Academy:
httpswww.netacad.comportalresourcespacket-tracer
(Requires a free NetAcad account)

Once opened, you can explore CLI configurations, test login behavior, and validate secure device access.

🧠 Lab created as part of my CCNA self-study journey.
Feel free to explore, copy, and practice!
