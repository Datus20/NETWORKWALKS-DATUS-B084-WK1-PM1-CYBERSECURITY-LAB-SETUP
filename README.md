# NETWORKWALKS-DATUS-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP
<div align="center">

# 🔐 Cybersecurity Lab Setup

**Building an isolated virtual lab for penetration testing and ethical hacking practice**
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Waqas%20Karim%20CCIE-C00000?style=flat-square" />
</p>

---

## 📌 Project Overview

This project focuses on setting up a **virtual cybersecurity and penetration-testing laboratory** using VirtualBox and Kali Linux.

The purpose of the lab is to create a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing activities can be performed safely and repeatedly.

The lab is configured on a private virtual network so that additional machines can be added later and used as targets for authorized security testing.

---


## 🎯 Objectives

The main objectives of this project are to:

- Install and configure VirtualBox.
- Install/import Kali Linux as a virtual machine.
- Create a private **NAT Network** for the cybersecurity lab.
- Configure network connectivity for Kali Linux.
- Assign a consistent IP address to the Kali and other VMs.
- Verify network connectivity and DNS resolution.
- Take a clean VM snapshot for recovery.
- Document the complete setup process.
- Prepare the environment for future cybersecurity projects.

---

## 🛡️ Purpose of the Lab

The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

It can be used for activities such as:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis
- Web security testing
- Exploitation practice
- Security-tool experimentation

⚠️ **Important:** This laboratory must only be used for systems that you own or have explicit permission to test. Do not use the lab or its tools to attack unauthorized systems.

---

## 🏗️ Lab Architecture
<img width="959" height="539" alt="11 Screenshot All VMS" src="https://github.com/user-attachments/assets/38f6070e-506d-460a-b3e1-438ec515eb4c" />

Additional target machines can be added to the same virtual network in future projects.

---

## ⚙️ Lab Configuration

| 🧩 Component       | ⚙️ Configuration   |
| ------------------ | ------------------  |
| 🖥️ Host OS         | Windows 11         |
| 🧠 Host RAM        | 8 GB               |
| ⚡ Processor       | Intel Core i5      |
| 🧰 Hypervisor      | VirtualBox 7.2.22  |
| 🐉 Security OS     | Kali Linux 2026.2  |
| 🧠 Kali RAM        | 4048 MB            |
| 🌐 Virtual Network | NAT Network        |
| 📡 Network Address | 10.0.0.0/24        |
| 🐧 Kali IP Address | 10.0.0.2/24        |
| 🚪 Default Gateway | 10.0.0.1           |
| 🌍 DNS Server      | 8.8.8.8            |
| 🔮 Future VM Range | 10.0.0.3–10.0.0.99 |

---

# 🪜 Lab Setup Procedure

## Step 1. Download ISO files for VMS(Kali,W7,W10 & Android x86)
The Virtual Machines was ISO files was Downloaded include as per below links,

  1.Kali https://cdimage.kali.org/kali-2026.3/kali-linux-2026.3-installer-amd64.iso
  
  2.Windows 10 https://www.microsoft.com/en-gb/software-download/windows10ISO
  
  3.Windows 7 https://getmyos.com/windows-7-multi-edition-checked-build-32-64-bit
  
  4.Android x86 https://www.fosshub.com/Android-x86.html

Note: Some Iso images are unofficial and can be used for lab preparation only do not use it on live Enterprise systems
---

## Step 2. Install VirtualBox

VirtualBox was installed as the hypervisor.

---

## Step 3. Create the NAT Network

A dedicated NAT Network was created in VirtualBox.

Configuration:
Network Name: NatNetwork
IPv4 Prefix:  10.0.0.0/24
DHCP:         Enabled
IPv6:         Disabled

<img width="959" height="539" alt="1 Screenshot-Virtual Box Network Config" src="https://github.com/user-attachments/assets/3f7faf74-d177-487d-b606-cebcac5f53ec" />

A **NAT Network** was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This will allow future attacker and target VMs to communicate within the lab.


---

## Step 4. Install Kali Linux

The Kali Linux virtual machine was downloaded from the official Kali Linux website and iinstalled VirtualBox.

The VM network adapter was configured as follows:

```text
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```

The VM was allocated:

```text
RAM: 4048 MB
```
<img width="959" height="539" alt="Kali VM" src="https://github.com/user-attachments/assets/6b045076-7b66-49ca-ad9f-dfd6326629f2" />

A shared folder was also configured for transferring required files between the host operating system and the Kali VM.



---

## Step 5. Configure the Kali Linux Network

The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

Example configuration:

```text
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
```

A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.

<img width="959" height="504" alt="2 Screenshot-Kali-VM Ip configuration" src="https://github.com/user-attachments/assets/23a3f120-c7e6-4882-88ff-2827210d6dbc" />


---

## Step 7. Create  windows 10 VM 

After Completing installation of Kali VM creation of another VM windows 10 was done using the ISO method and configured as per requirement with the Network Ip configuration as below,

```text
IP Address: 10.0.0.10
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
```
<img width="959" height="503" alt="3 Screenshot-W10 VM ipconfiguration" src="https://github.com/user-attachments/assets/05051d6a-04c2-42d8-90f7-b8fbb7fdc446" />

## Step 8. Create  windows 7 VM (Optional)

After Completing installation of W10 VM creation of another VM windows 7 was done using the ISO method and configured as per requirement with the Network Ip configuration as below,

```text
IP Address: 10.0.0.7
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
```
<img width="959" height="505" alt="4 Screenshot-W7 VM ip config" src="https://github.com/user-attachments/assets/98e7d55e-eaed-4193-ad96-97d697848bb5" />

## Step 9. Create  Android x86 VM (Optional)
After Completing installation of W7 VM creation of another VM Android x86 was done using the ISO method and configured as per requirement with the Network Ip configuration as below,

```text
IP Address: 10.0.0.9
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
```
<img width="958" height="503" alt="5 Screenshot Android IP config" src="https://github.com/user-attachments/assets/64cec766-61fe-4431-9144-14547ba5896c" />

# 🔎 Lab Verification
The test of pinging across all VMs were conducted the result was as follows

# 🔎 Pinging on kali to windows 10 (10.0.0.10) and Google DNS 
Result Screenshot (Succsessfully)
<img width="959" height="505" alt="6 Screenshot-Kali VM Ping Windows VM" src="https://github.com/user-attachments/assets/8ae2ee5d-5825-4137-a151-7e453099a005" />

# 🔎 Pinging on  windows 10 to kali (10.0.0.2) and Google DNS 
Result Screenshot (Succsessfully)
<img width="959" height="504" alt="8 Screenshot-W10 VM ping Kali VM   Google DNS" src="https://github.com/user-attachments/assets/4a837e85-4927-4fd2-a9ac-22534d38aad4" />

# 🔎 Pinging on  windows 7 to both kali (10.0.0.2), W10 (10.0.0.10)  and Google DNS 
Result Screenshot (Succsessfully)
<img width="959" height="504" alt="9 Screenshot-W7 VM ping other VM" src="https://github.com/user-attachments/assets/c6ac1e3b-a39e-4091-8747-38178638ddb7" />

# 🔎 Pinging on  Android x86 to both kali (10.0.0.2) and Google DNS 
Result Screenshot (Succsessfully)
<img width="959" height="502" alt="10 Screenshot Android ping to kali" src="https://github.com/user-attachments/assets/18903bfc-81f1-4b78-9cf8-6ea8a4b2fe27" />


# 🐞 Problems Encountered & Solutions

Documenting problems is an important part of the project.

## Problem 1. Pinging from Other VMS (Kali, Android) to Windows 10 VM fail

After manually configuring the IPv4 settings, at first pinging to windows 10 VM was fail which was due to the issue that by default windows 10  ICMP echoes was set to be disable on the (Windows Defender Firewall with  Advance security)  

The network connection was then restarted/rebooted and connectivity was tested again.

> **Important:** Network interface and connection names may differ between systems. Students should first identify their actual connection name before running an `nmcli` command.

---

## Problem 2. VirtualBox VT-x / Virtualization Error

The VM initially failed to start because hardware virtualization was disabled in the system firmware/BIOS.

The issue was resolved by:

1. Restarting the computer.
2. Entering BIOS/UEFI settings.
3. Enabling Intel VT-x / hardware virtualization.
4. Saving the configuration.
5. Restarting the computer.
6. Starting the Kali VM again.

After enabling virtualization, the VM started successfully.


---

# 💡 What I Learned

Through this project, I learned how to create and configure a virtual environment for cybersecurity practice.

The most important concepts I learned include:

### 1. NAT vs NAT Network

A standard NAT configuration and a NAT Network serve different purposes.

A NAT Network allows multiple VMs connected to the same virtual network to communicate with one another while providing network address translation for external connectivity.

This makes it useful for building a multi-machine cybersecurity laboratory.

### 2. Virtual Machine Networking

I learned how VirtualBox virtual network adapters connect virtual machines to different types of networks and how network configuration affects communication between machines.

### 3. Static IP Configuration

I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

### 4. VM Snapshots

I learned that a clean snapshot should be created **before performing risky or experimental activities**.

This provides a known-good recovery point for future cybersecurity exercises.

### 5. Documentation

I learned that documenting commands, configuration, screenshots, problems, and solutions is an important part of a professional cybersecurity project.

---

# 🔐 Security & Ethical Use

This laboratory is intended strictly for education purposes only.

---

# 🔗 Tools & Resources

- **7-Zip:** [https://7-zip.org/download.html](https://7-zip.org/download.html)
- **VirtualBox:** [https://virtualbox.org/wiki/Downloads](https://virtualbox.org/wiki/Downloads)
- **Kali Linux:** [https://kali.org/get-kali](https://kali.org/get-kali)

---

# 👤 Author

**Waqas Karim**\
Cybersecurity Professional B082

LinkedIn: [https://www.linkedin.com/in/waqaskarim/](https://www.linkedin.com/in/waqaskarim/)

---

## 📌 Project Information

**Program Name:** Cybersecurity at Networkwalks | **Week:** 01 | **Project:** Cybersecurity & Pentesting Lab Setup | **Repository:** GitHub
