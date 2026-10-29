<div align="center">

# 🔐 Cybersecurity Lab Environment Setup

**Building an isolated virtual lab for penetration testing and ethical hacking practice**
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.3-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Khairunnisya%20Lubis%20-C00000?style=flat-square" />
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
- Assign a consistent IP address to the Kali VM.
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

<img width="1536" height="1024" alt="00_VirtualBox Kali Linux Lab Blueprint" src="https://github.com/user-attachments/assets/ba33f0a8-5559-4dc2-888c-5be5b2a8bb4c" />


Additional target machines can be added to the same virtual network in future projects.

---

## ⚙️ Lab Configuration

| 🧩 Component       | ⚙️ Configuration   |
| ------------------ | ------------------  |
| 🖥️ Host OS         | Windows 10         |
| 🧠 Host RAM        | 8 GB               |
| ⚡ Processor       | Intel Core i7      |
| 🧰 Hypervisor      | VirtualBox 7.2  |
| 🐉 Security OS     | Kali Linux 2026.2  |
| 🧠 Kali RAM        | 2048 MB            |
| 🌐 Virtual Network | NAT Network        |
| 📡 Network Address | 10.0.0.0/24        |
| 🐧 Kali IP Address | 10.0.0.2/24        |
| 🚪 Default Gateway | 10.0.0.1           |
| 🌍 DNS Server      | 8.8.8.8            |
| 🔮 Future VM Range | 10.0.0.3–10.0.0.99 |

---

# 🪜 Lab Setup Procedure

## Step 1. Install 7-Zip

7-Zip was installed to extract the Kali Linux virtual-machine package, which may be distributed as a `.7z` archive.

**Tool:** 7-Zip

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

<img width="1365" height="765" alt="02_setup_subnet" src="https://github.com/user-attachments/assets/5bc6be70-40a6-4273-9778-aa3d7a032950" />


A **NAT Network** was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This will allow future attacker and target VMs to communicate within the lab.


---

## Step 4. Import Kali Linux

The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

The VM network adapter was configured as follows:

```text
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```

The VM was allocated:

```text
RAM: 2048 MB
```
<img width="1365" height="765" alt="04_shared_folders" src="https://github.com/user-attachments/assets/4616b519-24a1-40b4-8a90-aa50efc2a493" />


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

<img width="1365" height="718" alt="05_kali_linux_ip_addrs" src="https://github.com/user-attachments/assets/62e8728a-6313-4c13-bd45-c1f14b1aac7b" />


---

## Step 6. Create a Clean VM Snapshot

After completing the initial configuration, a VirtualBox snapshot was created.

<img width="1362" height="711" alt="07_snapshoot" src="https://github.com/user-attachments/assets/32184a99-7e04-46ee-92e3-f6b783c26c6a" />

The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.


---

# 🔎 Lab Verification

| ✅ Test                        | 🧾 Command                      | 🎯 Expected Result              |
| ----------------------------- | ------------------------------- | ------------------------------- |
| 🌐 Check IP address           | `ip a`                          | Correct Kali IP displayed       |
| 📡 Test gateway               | `ping 10.0.0.1`                 | Successful replies              |
| 🌍 Test Internet connectivity | `ping 8.8.8.8`                  | Successful replies              |
| 🔎 Test DNS resolution        | `nslookup networkwalks.com`     | Domain resolves                 |
| 🧰 Verify Nmap                | `nmap --version`                | Nmap version displayed          |
| 🔄 Verify snapshot            | Restore snapshot and run `ip a` | Baseline configuration restored |

### Example Results

<img width="1365" height="718" alt="06_kali_linux_full_internet" src="https://github.com/user-attachments/assets/600abe53-bdbb-4a57-8779-969a2310b596" />

---

# 🐞 Problems Encountered & Solutions

## Lab Setup: VirtualBox and Kali Linux

### 1. DNS Resolution Failure

**Status:** Resolved during testing

**Problem**

Initially, Kali Linux could reach the gateway and a public IP address, but it could not resolve domain names. Running the following command:

```bash
ping -c 4 google.com
```

returned the error:

```text
Temporary failure in name resolution
```

**Cause**

The DNS configuration was not working correctly. The `/etc/resolv.conf` file contained only a NetworkManager comment and no configured DNS server.

**Solution**

A temporary DNS configuration was applied using:

```bash
sudo sh -c 'printf "nameserver 1.1.1.1\nnameserver 8.8.8.8\n" > /etc/resolv.conf'
```

After applying this configuration, the domain connectivity test succeeded with 0% packet loss.

For the final project configuration, the DNS server was set to `8.8.8.8` to match the lab requirements.

**Result**

DNS resolution worked successfully during testing. However, manually editing `/etc/resolv.conf` is a temporary workaround because NetworkManager may overwrite the file. The final DNS configuration should be verified after reconnecting or restarting the virtual machine.

---

### 2. IP Address and Subnet Mask Configuration

**Status:** Configuration values verified

**Problem**

There was uncertainty about whether entering `255.255.255.0` instead of `/24` was correct.

**Explanation**

Both values represent the same subnet prefix:

| Parameter | Value |
|---|---|
| IP Address | `10.0.0.2` |
| Subnet Mask | `255.255.255.0` |
| CIDR Prefix | `/24` |
| Network Address | `10.0.0.0/24` |
| Default Gateway | `10.0.0.1` |

**Solution**

The subnet mask was kept as `255.255.255.0`, which is the correct dotted-decimal representation of `/24`.

**Result**

No change was required. The configured subnet mask is consistent with the lab's `10.0.0.0/24` network.

---

### 3. NetworkManager Connection Issues

**Status:** Final configuration requires verification

**Problem**

During troubleshooting, the `Wired connection 1` profile appeared inactive, and the `eth0` interface was previously reported as unmanaged. Messages related to saving the connection also appeared in the terminal.

**Troubleshooting Steps**

The following commands were used to inspect the network configuration:

```bash
ip -4 addr show eth0
ip route
```

The IPv4 settings were also inspected using the NetworkManager connection editor.

**Recommended Configuration**

The intended static IPv4 configuration is:

- Method: Manual
- Address: `10.0.0.2`
- Netmask: `255.255.255.0`
- Gateway: `10.0.0.1`
- DNS Server: `8.8.8.8`

**Result**

The expected IP address and network connectivity had been observed previously. However, the final NetworkManager configuration must be verified to confirm that the settings were successfully saved and persist after reconnecting.

---

### 4. NetworkManager Save Button Was Disabled

**Status:** Cause not conclusively identified

**Problem**

The **Save** button appeared greyed out in the IPv4 settings editor.

**Troubleshooting Steps**

The following steps were recommended:

1. Remove any empty address rows.
2. Select **Manual** if configuring a static IPv4 address.
3. Enter the required IP address, netmask, and gateway.
4. Set the DNS server to `8.8.8.8`.
5. Review the configuration and check whether the Save button becomes available.

**Result**

The exact cause of the disabled button was not confirmed. A disabled Save button can indicate that no changes are pending or that the editor has not accepted the current configuration. The final settings should be checked rather than assuming the changes were saved.

---

### 5. Windows–Kali Linux Shared Folder

**Status:** Shared folder mounted successfully

**Problem**

The project required a shared folder between the Windows host and the Kali Linux virtual machine.

**Solution**

The VirtualBox shared folder was configured as follows:

| Setting | Value |
|---|---|
| Host Folder | `C:\downloads` |
| Share Name | `downloads` |
| Auto-mount | Enabled |
| Read-only | Disabled |
| Kali Linux Mount Path | `/media/sf_downloads` |

The following commands were used to inspect the mounted folder:

```bash
ls /media
ls -la /media/sf_downloads
```

The `sf_downloads` directory appeared in the output, and the directory could be accessed without an error.

**Result**

The shared folder was mounted successfully. Since the folder was empty during the initial check, a further test can be performed by creating a file in `C:\downloads` and verifying that it appears in Kali Linux.

---

### 6. Network Connectivity Testing

**Status:** Basic connectivity tests passed

**Problem**

It was necessary to verify that Kali Linux could reach the virtual network gateway, access an external IP address, and resolve domain names.

**Commands Used**

```bash
ping -c 4 10.0.0.1
ping -c 4 1.1.1.1
ping -c 4 google.com
```

**Purpose of Each Test**

- `10.0.0.1`: Tests connectivity to the virtual network gateway.
- `1.1.1.1`: Tests IP connectivity to an external address.
- `google.com`: Tests DNS resolution and connectivity to the resolved address.

**Result**

All three tests had previously succeeded after the DNS issue was addressed.

Note that `1.1.1.1` was used as an additional connectivity test, not as a required project DNS setting. The final DNS configuration follows the lab module and uses `8.8.8.8`.

---

### 7. VirtualBox Integration and Snapshot

**Status:** Some items require final verification

**Configuration Completed or Prepared**

- Created a NAT Network named `NatNetwork`.
- Set the network prefix to `10.0.0.0/24`.
- Connected the Kali Linux network adapter to `NatNetwork`.
- Configured Shared Clipboard and Drag-and-Drop.
- Configured the Windows shared folder.

**Remaining Verification**

- Test clipboard and Drag-and-Drop functionality.
- Confirm that the final network settings persist after reconnecting.
- Create and verify the initial snapshot in VirtualBox.


The snapshot should serve as a baseline recovery point before performing additional cybersecurity lab activities.

---

## Summary of Troubleshooting Results

| No. | Issue | Status |
|---:|---|---|
| 1 | DNS resolution failure | Resolved during testing |
| 2 | Subnet mask and CIDR confusion | Clarified; values are equivalent |
| 3 | NetworkManager connection state | Final configuration requires verification |
| 4 | Disabled Save button | Cause not conclusively identified |
| 5 | Shared folder configuration | Mounted successfully |
| 6 | Gateway, external IP, and domain connectivity | Tests previously passed |
| 7 | Clipboard, Drag-and-Drop, and snapshot | Final verification required |

## Conclusion

The main technical issue encountered during the lab setup was DNS resolution failure. This was addressed with a temporary DNS configuration, after which domain connectivity succeeded. Additional troubleshooting involved understanding subnet mask notation, inspecting NetworkManager settings, and configuring the VirtualBox shared folder.

The basic network connectivity tests and shared folder mount were successful during testing. The final NetworkManager configuration, clipboard and Drag-and-Drop functionality, and initial VM snapshot should be verified before marking the entire lab setup as complete.

This report distinguishes between confirmed results and items that still require verification to maintain accurate project documentation.



# 💡 What I Learned

## What I Learned

Through this lab project, I gained practical experience in setting up a virtual environment for cybersecurity practice using Oracle VirtualBox and Kali Linux.

### 1. Virtualization Fundamentals
I learned how virtualization works and how to use Oracle VirtualBox to run Kali Linux as a guest operating system on a Windows host machine. I also learned the importance of allocating appropriate system resources, such as RAM, to a virtual machine.

### 2. Virtual Network Configuration
I learned how to create and configure a NAT Network in VirtualBox using the `10.0.0.0/24` network range. I also gained a better understanding of how virtual machines communicate through a virtual network gateway.

### 3. IP Addressing and Subnetting
I learned how to configure a static IPv4 address and understand the relationship between an IP address, subnet mask, CIDR notation, and network address.

The network configuration used in this lab was:

- **IP Address:** `10.0.0.2`
- **Subnet Mask:** `255.255.255.0`
- **CIDR Prefix:** `/24`
- **Network Address:** `10.0.0.0/24`
- **Default Gateway:** `10.0.0.1`
- **DNS Server:** `8.8.8.8`

### 4. Network Connectivity Testing
I learned how to use basic Linux networking commands to inspect network interfaces, routing tables, and connectivity.

Commands practiced included:

```bash
ip -4 addr show eth0
ip route
ping -c 4 10.0.0.1
ping -c 4 8.8.8.8
ping -c 4 google.com
```

These commands helped me understand how to verify IP configuration, test gateway connectivity, check external IP connectivity, and identify DNS resolution problems.

### 5. DNS Troubleshooting
I learned the difference between IP connectivity and DNS resolution. A system may be able to reach an external IP address but still fail to access a domain name if DNS is not configured correctly.

By investigating the `/etc/resolv.conf` file and testing DNS resolution, I gained practical experience diagnosing and troubleshooting a basic networking issue.

### 6. Shared Folders and Virtual Machine Integration
I learned how to configure a VirtualBox shared folder to exchange files between the Windows host and the Kali Linux guest system.

The shared folder was configured using `C:\downloads` on Windows and mounted at `/media/sf_downloads` in Kali Linux.

I also learned where to configure Shared Clipboard and Drag-and-Drop integration in VirtualBox.

### 7. Virtual Machine Snapshots
I learned the purpose of VirtualBox snapshots and how they can provide a recovery point before making further changes to a virtual machine.

An initial snapshot named `clean-kali (network setup)` was planned as a baseline for future cybersecurity lab activities.

### 8. Technical Documentation and Troubleshooting
I learned the importance of documenting configuration settings, terminal commands, test results, and troubleshooting steps. Clear documentation makes it easier to reproduce a setup, investigate problems, and communicate technical findings.

### Key Takeaway

This project strengthened my foundational knowledge of Linux, virtualization, IPv4 networking, DNS, and basic troubleshooting. It also helped me develop a more systematic approach to configuring and documenting a cybersecurity lab environment.

These skills provide a foundation for future cybersecurity exercises involving network analysis, security testing, and isolated virtual lab environments.


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

**Khairunnisya Lubis**\
Cybersecurity Student B084D

LinkedIn: [![LinkedIn](https://shields.io)](https://www.linkedin.com/in/khairunnisya-lubis-s-farm-761728336/)

---

## 📌 Project Information

**Program Name:** Cybersecurity at Networkwalks | **Week:** 01 | **Project:** Cybersecurity & Pentesting Lab Setup | **Repository:** GitHub

