# Azure Network Protocols & Traffic Analysis

This lab explores the configuration of Network Security Groups (NSGs) to control inbound and outbound traffic within an Azure Virtual Network. Additionally, I utilize Wireshark to perform deep packet inspection of various networking protocols to understand how data is transmitted and secured.

## 🛡️ Network Security & Firewalls

In this section, I configured Layer 4 firewall rules (NSGs) to observe how traffic is filtered between virtual machines.

* **NSG Configuration:** Creating a specific inbound security rule to deny ICMP traffic.
<img width="1657" alt="01_Azure_NSG_Rule" src="https://github.com/user-attachments/assets/5ce20a29-b267-4d24-b763-6cfe47898c23" />

* **Deny Rule Verification:** Testing the rule by attempting to ping a VM from another machine. The "Request timed out" confirms the firewall is actively blocking ICMP.
<img width="1129" alt="02_ICMP_Blocked_Test" src="https://github.com/user-attachments/assets/63af8ff0-6a35-4be8-9d98-ba08073210f0" />

---

## 🔍 Deep Packet Inspection (Wireshark)

Using Wireshark, I inspected live traffic to analyze how different protocols behave on the wire.

* **SSH Encryption:** Observing the encrypted payload of an SSH session. This highlights why SSH is the standard for secure remote management over unencrypted protocols like Telnet.
<img width="1308" alt="03_SSH_Wireshark_Encryption" src="https://github.com/user-attachments/assets/374b093f-7cbf-48e1-ab59-182b80856853" />

* **RDP Traffic Analysis:** Inspecting the constant stream of Remote Desktop Protocol (RDP) traffic.
<img width="1716" alt="06_RDP_Traffic_Analysis" src="https://github.com/user-attachments/assets/3172febe-c767-4fa8-98e6-b442785e1a92" />

---

## 🌐 Network Infrastructure Services

I analyzed the fundamental background services that allow devices to communicate and resolve addresses.

* **DNS Resolution:** Using `nslookup` to trigger DNS queries and inspecting the recursive lookup process within Wireshark.
<img width="1509" alt="04_DNS_NSLookup_Results1" src="https://github.com/user-attachments/assets/afb39803-f4a7-4482-b763-4073001eddb2" />

* **DHCP DORA Process:** Capturing the Discover, Offer, Request, and Acknowledge (DORA) sequence when a workstation requests an IP address from a DHCP server.
<img width="985" alt="05_DHCP_DORA_Capture2" src="https://github.com/user-attachments/assets/5f5cdfc0-2383-4897-9226-acef567c069c" />
