# 📌 Project Summary
This project centers on building a virtual cybersecurity and penetration-testing lab with VirtualBox and Kali Linux.
The lab exists to provide a controlled space where security tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing tasks can be carried out safely and repeatedly.
The lab runs on a private virtual network, allowing further machines to be added down the line and used as targets for authorized security testing.
________________________________________
# 🎯 Goals
The key goals of this project are to:
•	Install and set up VirtualBox.
•	Install or import Kali Linux as a virtual machine.
•	Build a private NAT Network for the security lab.
•	Set up network connectivity for Kali Linux.
•	Give the Kali VM a fixed IP address.
•	Confirm network connectivity and DNS resolution.
•	Capture a clean VM snapshot for recovery purposes.
•	Record the entire setup process.
•	Get the environment ready for future cybersecurity projects.
________________________________________
# 🛡️ Lab Purpose
The lab offers a separated, controlled space for learning cybersecurity and for authorized security testing.
It supports activities including:
•	Network reconnaissance
•	Port scanning
•	Vulnerability assessment
•	Packet analysis
•	Web security testing
•	Exploitation practice
•	Security-tool experimentation
⚠️ Note: Only use this laboratory against systems you own or have explicit permission to test. Never use the lab or its tools to attack systems without authorization.
________________________________________
# 🏗️ Lab Layout

![image alt](https://github.com/Chims79/NETWORKWALKS-B083B-Cyber-Security-Pen-Testing-Wk1-Lab-Setup-/blob/3bc4807b53572edb3875430d238abb7510377fd4/1-lab-architecture.jpeg)

Further target machines can be added to this same virtual network in later projects.
________________________________________
⚙️ Lab Settings
🧩 Component	⚙️ Configuration
🖥️ Host OS	Windows 11
🧠 Host RAM	16 GB
⚡ Processor	Intel Core i5
🧰 Hypervisor	VirtualBox 7.2
🐉 Security OS	Kali Linux 2026.2
🧠 Kali RAM	2048 MB
🌐 Virtual Network	NAT Network
📡 Network Address	10.0.0.0/24
🐧 Kali IP Address	10.0.0.2/24
🚪 Default Gateway	10.0.0.1
🌍 DNS Server	8.8.8.8/10.0.0.1
🔮 Future VM Range	10.0.0.3–10.0.0.99
________________________________________
# 🪜 Lab Setup Steps
### Step 1. Install 7-Zip
7-Zip was used to unpack the Kali Linux virtual-machine package, since it may come as a .7z archive.
Tool: 7-Zip
________________________________________
### Step 2. Install VirtualBox
VirtualBox was set up to serve as the hypervisor.
________________________________________
Step 3. Create the NAT Network
A dedicated NAT Network was built within VirtualBox.
Configuration: Network Name: NatNetwork IPv4 Prefix: 10.0.0.0/24 DHCP: Enabled IPv6: Disabled


![image alt](https://github.com/Chims79/NETWORKWALKS-B083B-Cyber-Security-Pen-Testing-Wk1-Lab-Setup-/blob/d27f5b7d41cd3f00f77f3969f36382a5c7c3b7a5/2-nat-network-config.png)











A NAT Network was chosen because several virtual machines joined to the same NAT Network can talk to each other while still reaching the outside network.
This lets future attacker and target VMs exchange traffic within the lab.
________________________________________
### Step 4. Import Kali Linux
The Kali Linux virtual machine was pulled from the official Kali Linux website and brought into VirtualBox.
The VM’s network adapter was set up as shown below:
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
The VM was allocated:
RAM: 2048 MB

![image alt](https://github.com/Chims79/NETWORKWALKS-B083B-Cyber-Security-Pen-Testing-Wk1-Lab-Setup-/blob/516fd4f85f498e67c69d7531dd7afc499bcbab05/3-kali-desktop.png)











 A shared folder was also set up to move needed files between the host operating system and the Kali VM.




________________________________________
### Step 5. Configure the Kali Linux Network
The Kali Linux network settings were reviewed and set with a fixed IPv4 address.
Example configuration:
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8/10.0.0.1


A fixed IP address makes the lab easier to document and lets the Kali machine be referenced consistently in later exercises.

________________________________________
Step 6. Create a Clean VM Snapshot
Once the initial setup was finished, a VirtualBox snapshot was taken.
Example snapshot name:
Clean Kali - Network Setup
The snapshot serves as the clean baseline for the laboratory.
Should a later exercise alter or break the VM configuration, the machine can be reverted to this baseline.
________________________________________
🔎 Lab Verification
✅ Test	🧾 Command	🎯 Expected Result
🌐 Check IP address	ip a	Correct Kali IP displayed
📡 Test gateway	ping 10.0.0.1	Successful replies
🌍 Test Internet connectivity	ping 8.8.8.8	Successful replies
🔎 Test DNS resolution	nslookup networkwalks.com	Domain resolves
🧰 Verify Nmap	nmap --version	Nmap version displayed
🔄 Verify snapshot	Restore snapshot and run ip a	Baseline configuration restored

Example Results
IP Address:
10.0.0.2/24

Gateway:
10.0.0.1

DNS:
8.8.8.8
________________________________________
# 🐞 Issues Encountered & Fixes
Keeping a record of problems is a key part of the project.
Issue 1. Internet Connectivity After Static IP Configuration
Once the IPv4 settings are set manually, Internet access can sometimes fail depending on the Kali/NetworkManager setup.
One fix applied during this lab was:
I included both 8.8.8.8/10.0.0.1 DNSs
After this the network network connection was t restarted and connectivity was restored.
Note: Network interface and connection names can vary from system to system. Students should confirm their actual connection name before running any nmcli command.
________________________________________

### Issue 2. Typing this project in the repository
I had challenge on how to type this project in GitHub until I watched videos on YouTube on how to type in the repository.

________________________________________
# 💡 Key Takeaways
This project taught me how to build and set up a virtual environment for cybersecurity practice.
The most important lessons include:
1. NAT vs NAT Network
A standard NAT setup and a NAT Network each serve a different purpose.
A NAT Network lets several VMs on the same virtual network talk to one another while still providing address translation for outside connectivity.
This makes it well suited for building a multi-machine cybersecurity lab.
2. Virtual Machine Networking
I learned how VirtualBox’s virtual network adapters link virtual machines to different network types, and how network settings shape communication between machines.
3. Static IP Configuration
I learned how to set up and check IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.
4. VM Snapshots
I learned that a clean snapshot ought to be taken before carrying out risky or experimental tasks.
This gives a reliable recovery point for future cybersecurity exercises.
5. Documentation
I learned that recording commands, settings, screenshots, problems, and fixes is a vital part of a professional cybersecurity project.
________________________________________
# 🔐 Security & Responsible Use
This laboratory is meant strictly for educational purposes only.
________________________________________
🔗**Tools & Links**
•	7-Zip: https://7-zip.org/download.html
•	VirtualBox: https://virtualbox.org/wiki/Downloads
•	Kali Linux: https://kali.org/get-kali
________________________________________

# 👤 Author
**Chimanda P Mbangweta**
Cybersecurity Professional B083B
LinkedIn:  https://www.linkedin.com/in/chimanda-p-mbangweta-45972772

________________________________________
# 📌Project Information
**Program Name:** ***Cybersecurity at Networkwalks | Week: 01 | Project: Cybersecurity & Pentesting Lab Setup | Repository: GitHub*






