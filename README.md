# Internship Project
# Task 5 - 📡 Network Traffic Analysis with Wireshark
# 📝 Project Overview
This project focuses on capturing and analyzing live network traffic using Wireshark to understand communication patterns, detect active protocols, and identify potential security issues in a controlled lab environment.

Goal: Observe and interpret real-time network packets, recognize different protocols in use, and evaluate the security posture of the traffic flow.

# 🛠 Tools & Environment
Wireshark – Open-source packet sniffer & protocol analyzer

Target Website: http://testhtml5.vulnweb.com/#/popular

# Protocols Breakdown

## Total packets captured - 3623

# Key Analysis of Captured Protocols

1. ARP (Address Resolution Protocol)

Traffic Observed: 6 ARP request/reply packets.

Purpose: Resolved MAC-to-IP mappings within the VMware virtual network.

Security Note: Normal behavior, but ARP spoofing could be a potential risk in larger networks.

2. DNS (Domain Name System)

Traffic Observed: 200 query/response packets for domains including google.com, tesla.com, facebook.com, acunetix.com.

Purpose: Mapped domain names to IP addresses for communication.

Security Note: Queries were in plaintext (UDP port 53); susceptible to DNS spoofing or interception without DNSSEC.

3. HTTP (Hypertext Transfer Protocol)

Traffic Observed: 80 request/response packets to host testhtml5.vulnweb.com.

Methods Used: GET, POST.

Key Issue: No encryption (HTTP instead of HTTPS); sensitive form data visible in plain text, making it vulnerable to interception.

4. ICMP (Internet Control Message Protocol)

Traffic Observed: 30 echo requests/replies (ping to tesla.com).

Purpose: Used for connectivity checks and diagnostics.

Security Note: Normal for troubleshooting; excessive ICMP could indicate reconnaissance or DoS attempts.

5. TCP (Transmission Control Protocol)

Traffic Observed: 1,849 packets (~51% of all captured traffic).

Purpose: Provided reliable delivery of HTTP, DNS, and other application data.

Key Features: Three-way handshake, sequencing, acknowledgments.

Security Note: Core transport protocol; potential risk if unencrypted application data is carried.


#  Step-by-Step Process
Environment Setup

Installed Wireshark on VMware virtual machine 

sudo apt install wireshark
Configured network interface for packet capture
Traffic Generation

Browsed http://testhtml5.vulnweb.com/#/popular
Performed DNS lookups (google.com, facebook.com,tesla.com,acunetix.com)
Submitted forms with test data
Packet Capture

Duration: ~1 minute
Total packets: 3623
Interface: VMware virtual network adapter
Analysis Techniques

Protocol filtering (http, dns, arp,tcp,imps)
Statistical analysis using Wireshark
Packet-level inspection and data extraction


# 🎯 Skills & Expertise Gained
# Core Skills
🔍 Protocol Investigation – Examined and interpreted multiple network protocols in detail.

🛡️ Security Evaluation – Identified significant weaknesses in data transmission and network setup.

📊 Traffic Flow Analysis – Recognized and understood normal vs. abnormal web application communication patterns.

🕵️ Digital Forensics – Retrieved and examined sensitive information from captured network packets.

# Technical Proficiencies
⚡ Wireshark Mastery – Hands-on experience in live packet capturing and detailed packet inspection.

🔧 Filter Utilization – Applied protocol filters and statistical tools for targeted traffic analysis.

🚨 Threat Detection – Pinpointed potential attack vectors and unprotected data flows.

📝 Reporting & Documentation – Produced structured and clear reports summarizing findings.

# 🚀 Suggested Improvements & Next Steps

Investigate encrypted traffic such as HTTPS/TLS for advanced inspection techniques.

Explore additional protocols (SMTP, FTP, SSH) for broader analysis capabilities.

Implement automated tools/scripts to detect suspicious packet patterns.

Develop baseline traffic behavior profiles to spot anomalies quickly.

Set up continuous network monitoring for proactive threat detection.

Advanced Techniques to Explore

Deep Packet Inspection (DPI) for detailed application-layer analysis.

Network Behavior Analysis (NBA) to identify unusual traffic activities.

Integrate Threat Intelligence feeds to detect known malicious entities.

Apply Machine Learning models for automated pattern recognition in live environments.
