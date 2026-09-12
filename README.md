# **CYBERSECURITY LAB ENVIRONMENT SETUP**

Building an isolated virtual lab for penetration testing an ethical hacking practice


## **Project Overview**

This project focuses on setting up a virtual cybersecurity and penetration-testing laboratory using VirtualBox and Kali Linux.
The purpose of the lab is to create a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing activities can be performed safely and repeatedly.
The lab is configured on a private virtual network so that additional machines can be added later and used as targets for authorized security testing.

## **Project Objectives**

**The main objectives of this project are to:**

•	Install and configure VirtualBox.

•	Install/import Kali Linux as a virtual machine.

•	Create a private NAT Network for the cybersecurity lab.

•	Configure network connectivity for Kali Linux.

•	Assign a consistent IP address to the Kali VM.

•	Verify network connectivity and DNS resolution.

•	Take a clean VM snapshot for recovery.

•	Document the complete setup process.

•	Prepare the environment for future cybersecurity projects.

## **Purpose of The Lab**

The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.
It can be used for activities such as:
•	Network reconnaissance
•	Port scanning
•	Vulnerability assessment
•	Packet analysis
•	Web security testing
•	Exploitation practice
•	Security-tool experimentation


## **Lab Structure**

<img width="1920" height="922" alt="VirtualBox_kali-linux-2026 2-virtualbox-amd64_12_09_2026_07_28_21" src="https://github.com/user-attachments/assets/527bf7f5-cb35-4c74-be87-01d828d9eeb7" />

 


## **Lab Configuration**

<img width="806" height="443" alt="Screenshot (3)" src="https://github.com/user-attachments/assets/16878df3-3a5d-4fbf-b9fc-ee87b5da4bca" />


## **Lab Setup Procedure**

### **Step 1. Install 7-Zip**

7-Zip was installed to extract the Kali Linux virtual-machine package, which may be distributed as a .7z archive.
Tool: 7-Zip

### **Step 2. Install VirtualBox**

VirtualBox was installed as the hypervisor.

### **Step 3. Create the NAT Network**

A dedicated NAT Network was created in VirtualBox.
Configuration: Network Name: NatNetwork IPv4 Prefix: 10.0.0.0/24 DHCP: Enabled IPv6: Disabled


<img width="1920" height="1021" alt="Screenshot (1)" src="https://github.com/user-attachments/assets/afe79aef-8c89-4b21-90ef-b2cfbcedec5e" />
<img width="1920" height="1017" alt="Screenshot (2)" src="https://github.com/user-attachments/assets/275eb63e-5d7f-4204-be1b-01d73b6660ed" />


A NAT Network was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.
This will allow future attacker and target VMs to communicate within the lab.

### **Step 4. Import Kali Linux**

The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.
The VM network adapter was configured as follows:

```Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```
 
The VM was allocated:

`RAM: 4096 MB
 `
### **Step 5. Configure the Kali Linux Network**

The Kali Linux network configuration was checked and configured with a consistent IPv4 address.
Example configuration:
 
A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.

 <img width="1920" height="922" alt="VirtualBox_kali-linux-2026 2-virtualbox-amd64_12_09_2026_07_29_22" src="https://github.com/user-attachments/assets/1a949b36-1208-4a3d-8e0a-ffca7938c4c4" />


### **Step 6. Create a Clean VM Snapshot**

After completing the initial configuration, a VirtualBox snapshot was created.

**Example snapshot name:**

`Clean Kali - Network Setup`
 
The snapshot represents the clean baseline of the laboratory.
If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

## **Lab Verification**

<img width="1001" height="329" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/9a5bc1ec-f8e0-49f8-8049-5019c64563cc" />


### **Test	Command	Expected Result**

Check IP address	ip a	Correct Kali IP displayed
Test gateway	ping 10.0.0.1	Successful replies
Test Internet connectivity	ping 8.8.8.8	Successful replies
 Verify Nmap	nmap --version	Nmap version displayed
Verify snapshot	Restore snapshot and run ip a	Baseline configuration restored

**Example Results**

```IP Address:
10.0.0.2/24

Gateway:
10.0.0.1

DNS:
8.8.8.8, 10.0.0.1
```

 

## **Problems Encountered & Solutions**

I Had Problem With Internet Connectivity After Static IP Configuration
After manually configuring the IPv4 settings, my internet connectivity failed.

## **How I solved it:**

I opened the terminal in kali linux and entered the code below:

 `sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0`

 <img width="1920" height="922" alt="VirtualBox_kali-linux-2026 2-virtualbox-amd64_12_09_2026_07_22_45" src="https://github.com/user-attachments/assets/627508dc-3173-4f98-a270-781a1e6bb610" />

 
The network connection was then restarted/rebooted and connectivity was tested again.

## **What I Learned**

Through this project, I learned how to create and configure a virtual environment for cybersecurity practice.
The most important concepts I learned include:

### **1. NAT vs NAT Network**

A standard NAT configuration and a NAT Network serve different purposes.
A NAT Network allows multiple VMs connected to the same virtual network to communicate with one another while providing network address translation for external connectivity.
This makes it useful for building a multi-machine cybersecurity laboratory.

### **2. Static IP Configuration**

I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

### **3. VM Snapshots**

I learned that a clean snapshot should be created before performing risky or experimental activities.
This provides a known-good recovery point for future cybersecurity exercises.

### **4. Documentation**

I learned that documenting commands, configuration, screenshots, problems, and solutions is an important part of a professional cybersecurity project.

## **Security & Ethical Use**

This laboratory is intended strictly for education purposes only.

## **Tools & Resources**

•	7-Zip: https://7-zip.org/download.html

•	VirtualBox: https://virtualbox.org/wiki/Downloads

•	Kali Linux: https://kali.org/get-kali

## **Author**

**Agbango Nehemiah Awindin**

**Waqas Karim**

Cybersecurity Professional B082

LinkedIn: https://www.linkedin.com/in/waqaskarim/

## **Project Information**

Program Name: Cybersecurity at Networkwalks | Week: 01 | Project: Cybersecurity & Pentesting Lab Setup | Repository: GitHub


