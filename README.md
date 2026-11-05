# 🔐 Cybersecurity Internship – B084 | Week 1: Cyber Lab Setup and Configuration

<div align="center">

**Building My Virtual Cybersecurity Lab for Hands-On Learning, Ethical Hacking, and Penetration Testing**

![Cybersecurity](https://img.shields.io/badge/Field-Cybersecurity-red)
![VirtualBox](https://img.shields.io/badge/VirtualBox-7.2-blue)
![Kali Linux](https://img.shields.io/badge/Kali_Linux-2026.2-orange)
![Networking](https://img.shields.io/badge/Networking-NAT_Network-green)
![Internship](https://img.shields.io/badge/Internship-B084-blue)

</div>

---

## 📌 Project Overview

As part of my NetworkWalks Cybersecurity Internship (B084), my first-week project focuses on building a virtual cybersecurity laboratory using Oracle VirtualBox and Kali Linux.

My goal is to create a safe and controlled environment where I can practice cybersecurity techniques, improve my technical skills, and gain hands-on experience working with security tools.

The lab will allow me to perform network reconnaissance, port scanning, vulnerability assessments, and other authorized security testing activities without interfering with production systems.

I am using a private NAT Network so I can add more virtual machines in future projects and practice how different systems communicate within a network.

---

## 🎯 Project Objectives

The main objectives of my Week 1 project are to:

- Install and configure Oracle VirtualBox.
- Install and set up Kali Linux as a virtual machine.
- Create a dedicated NAT Network for my cybersecurity lab.
- Configure the network adapter and connectivity settings.
- Assign a consistent IP address to my Kali Linux machine.
- Verify network connectivity and DNS resolution.
- Create a clean virtual machine snapshot for recovery.
- Document my installation process, configurations, and troubleshooting steps.
- Prepare the environment for future cybersecurity exercises.

---

## 🛡️ Purpose of My Cybersecurity Lab

I am building this lab to strengthen my practical knowledge of cybersecurity, Linux administration, and computer networking.

Having a virtual environment allows me to experiment with different tools, troubleshoot technical problems, and learn from mistakes without putting real systems at risk.

### Activities I Plan to Practice

- **Network Reconnaissance:** Identifying devices, services, and network information.
- **Port Scanning:** Discovering open ports and understanding running services.
- **Vulnerability Assessment:** Identifying potential security weaknesses.
- **Packet Analysis:** Monitoring and analyzing network traffic.
- **Web Application Security:** Understanding common web application vulnerabilities.
- **Penetration Testing:** Practicing authorized ethical hacking techniques.
- **Security Tools:** Exploring Nmap, Wireshark, Burp Suite, and other Kali Linux tools.

> ⚠️ **Ethical Use:** I will only perform security testing on systems that I own or have explicit permission to assess.

---

## 🏗️ Lab Architecture

The following diagram illustrates the planned structure of my cybersecurity lab.

![My Cybersecurity Lab Architecture](Lab%20Architecture.png)

My lab uses Oracle VirtualBox to run Kali Linux on a private NAT Network.

As I progress through the internship, I plan to add more virtual machines to simulate real-world networking and cybersecurity scenarios.

---

## ⚙️ Lab Configuration

The following configuration is based on the reference lab setup and should be checked against my actual environment.

| 🧩 Component | ⚙️ Configuration |
|---|---|
| 🖥️ Host Operating System | Windows 10 |
| 🧠 Host Memory | 8 GB RAM |
| ⚡ Processor | Intel Core i7 |
| 🧰 Virtualization Software | Oracle VirtualBox 7.2 |
| 🐉 Security Operating System | Kali Linux 2026.2 |
| 💾 Kali Linux Memory | 2048 MB |
| 🌐 Network Type | NAT Network |
| 📡 Network Address | 10.0.0.0/24 |
| 🐧 Kali Linux IP | 10.0.0.2/24 |
| 🚪 Default Gateway | 10.0.0.1 |
| 🌍 DNS Server | 8.8.8.8 |
| 🔮 Planned Additional VM Range | 10.0.0.3–10.0.0.99 |

---

# 🪜 Lab Setup Procedure

## Step 1: Installing 7-Zip

The first step in my lab setup is installing 7-Zip.

I need this application to extract compressed files, especially Kali Linux virtual machine images distributed in the `.7z` format.

**Tool Used:** 7-Zip

---

## Step 2: Installing Oracle VirtualBox

Next, I install Oracle VirtualBox, which allows me to create and manage virtual machines on my computer.

VirtualBox provides the platform I need to run Kali Linux without replacing my main operating system.

---

## Step 3: Creating My NAT Network

To support communication between virtual machines, I configure a dedicated NAT Network in VirtualBox.

### Network Settings

```text
Network Name: NatNetwork
IPv4 Prefix: 10.0.0.0/24
DHCP: Enabled
IPv6: Disabled
```

![VirtualBox NAT Network Configuration](2-screenshot-network-settings-1.png)

I selected NAT Network because it allows virtual machines on the same virtual network to communicate with one another while supporting outbound internet connectivity.

This will be useful when I introduce additional test machines later in my internship.

---

## Step 4: Importing Kali Linux

After configuring VirtualBox, I download the Kali Linux virtual machine image from the official Kali Linux website.

I then import the machine into VirtualBox and adjust its settings.

### Virtual Network Adapter

```text
Adapter 1
Attached to: NAT Network
Network: NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```

### Allocated Memory

```text
RAM: 2048 MB
```

![Kali Linux Virtual Machine](3-screenshot-kali-linux.png)

I also configure a shared folder where appropriate to make it easier to transfer necessary files between my host computer and Kali Linux.

---

## Step 5: Configuring Kali Linux Networking

Once Kali Linux is running, I check its network settings and configure a consistent IPv4 address for the lab.

### Network Configuration

```text
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Default Gateway: 10.0.0.1
DNS Server: 8.8.8.8
```

![Kali Linux Network Settings](4-screenshot-kali-network-settings.png)

Using a consistent IP address makes it easier for me to identify the Kali Linux machine and connect it to additional virtual machines during future exercises.

---

## Step 6: Creating a Clean Virtual Machine Snapshot

After completing the initial setup, I create a snapshot in VirtualBox.

### Snapshot Name

```text
Clean Kali - Network Setup
```

This snapshot serves as my recovery point.

If I make changes that affect the virtual machine or encounter problems during future cybersecurity exercises, I can restore the machine to its original working configuration.

---

# 🔎 Lab Verification

After configuring my lab, I use the following commands to check whether the network and security tools are functioning correctly.

| ✅ Verification Test | 🧾 Command | 🎯 Expected Result |
|---|---|---|
| Check Kali IP address | `ip a` | Displays the configured IP address |
| Test default gateway | `ping 10.0.0.1` | Receives successful replies |
| Test internet connectivity | `ping 8.8.8.8` | Receives successful replies |
| Verify DNS resolution | `nslookup networkwalks.com` | Resolves the domain |
| Check Nmap installation | `nmap --version` | Displays installed Nmap version |
| Verify snapshot recovery | Restore snapshot and run `ip a` | Confirms baseline configuration |

### Expected Network Information

```text
IP Address:
10.0.0.2/24

Default Gateway:
10.0.0.1

DNS Server:
8.8.8.8
```

These are expected values based on the reference configuration, not recorded verification results.

---

# 🐞 Troubleshooting and Possible Solutions

Troubleshooting is an important part of my cybersecurity training because it helps me understand how systems behave when configurations are incorrect.

## Problem 1: Internet Connectivity After Configuring a Static IP

One possible issue is losing internet connectivity after manually changing Kali Linux network settings.

A troubleshooting option from the reference lab is:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
```

After applying the appropriate network configuration, I can restart the connection and test connectivity again.

**Important:** The connection name may be different on my system, so I must verify the correct name before running the command.

## Problem 2: VirtualBox Hardware Virtualization Error

Another possible challenge is VirtualBox failing to start Kali Linux because hardware virtualization is disabled.

### Troubleshooting Steps

1. Restart the computer.
2. Open the BIOS or UEFI settings.
3. Locate the hardware virtualization option.
4. Enable Intel VT-x or the applicable virtualization feature.
5. Save the settings.
6. Restart the computer.
7. Try launching Kali Linux again.

These steps provide a troubleshooting reference if I encounter this issue.

---

# 💡 What I Learned

This project is helping me understand the practical steps involved in preparing a cybersecurity testing environment.

### 1. NAT vs. NAT Network

I learned that standard NAT and NAT Network are not exactly the same.

NAT Network is especially useful for a cybersecurity lab because multiple virtual machines connected to it can communicate with one another.

### 2. Virtual Machine Networking

I gained a better understanding of how virtual network adapters work and how network settings determine communication between machines.

### 3. IP Address Configuration

I practiced working with IPv4 addresses, subnet masks, default gateways, and DNS settings.

### 4. Virtual Machine Snapshots

I learned why it is important to create a clean recovery point before performing experiments that could affect system stability.

### 5. Technical Documentation

I also learned the importance of documenting configurations, commands, screenshots, challenges, and troubleshooting procedures.

Good documentation makes it easier to repeat a setup, resolve problems, and demonstrate technical knowledge.

---

# 🔐 Security and Ethical Considerations

My cybersecurity lab is intended strictly for educational purposes and authorized security testing.

I understand that cybersecurity professionals have a responsibility to protect systems, respect privacy, and follow ethical standards.

All security testing will be performed within my own laboratory or on systems for which I have explicit authorization.

---

# 🔗 Tools and Resources

- **7-Zip:** https://7-zip.org/download.html
- **Oracle VirtualBox:** https://virtualbox.org/wiki/Downloads
- **Kali Linux:** https://kali.org/get-kali

---

# 👤 About This Project

This project is part of my practical cybersecurity training through the NetworkWalks Cybersecurity Internship.

My focus is on developing real-world skills in cybersecurity operations, network security, virtualization, Linux administration, vulnerability assessment, and ethical hacking.

---

## 📌 Project Information

| Item | Details |
|---|---|
| Program | NetworkWalks Cybersecurity Internship |
| Batch | B084 |
| Week | 01 |
| Project | Cybersecurity Lab Setup and Configuration |
| Tools | Oracle VirtualBox and Kali Linux |
| Documentation | GitHub README |
| Project Type | Hands-On Cybersecurity Lab |

---

## ✅ Conclusion

Completing this lab setup will give me a foundation for future cybersecurity projects.

It will allow me to continue practicing security tools, exploring network configurations, and developing the technical skills needed for real-world cybersecurity work.

My goal is to keep improving through practical experience, continuous learning, and responsible cybersecurity practices.
