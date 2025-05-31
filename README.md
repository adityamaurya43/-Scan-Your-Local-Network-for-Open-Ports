# -Scan-Your-Local-Network-for-Open-Ports

# Key Concepts:
Port Scanning
TCP SYN Scan
IP Ranges
Network Reconnaissance
Open Ports
Network Security Basics


# Install Nmap from the official Kali repo
Nmap was already installed and used.
Version: 7.95

# Run a TCP SYN Scan
Command: nmap -sS -v 192.168.232.128/24
Action: Scans all 255 IPs in the subnet using SYN (half-open) method

# Find your local IP range
Command: ifconfig
Interface: eth0
Local IP: 192.168.232.128
Subnet: /24 → IP Range: 192.168.232.0/24

# Open ports discovered
192.168.232.2: 532/tcp, 912/tcp, 5357/tcp
192.168.232.1: 53/tcp

# Research Services
Port 53: DNS
Port 5357: Web Services for Devices
Port 912: Commonly used for remote access/tools
Port 532: Possibly custom or proprietary service

# Analyze with Wireshark
Tool used: Wireshark
Filter: ip.addr == 192.168.232.128
Observed DNS and TLS traffic, TCP SYN packets, etc

# Security Risk Identification
Open ports expose attack surface
Unsecured services may allow remote access or vulnerabilities

# Scan Result Export: Ifyou want to save the result in file
Can be saved using -oN for normal text, -oX for XML, -oA for all
Example: nmap -sS 192.168.232.128/24 -oN scan_results.txt

# Conclusion
This assignment demonstrated how to perform a TCP SYN scan using Nmap in Kali Linux, analyze live traffic using Wireshark, and interpret the output to identify security risks from open ports. These skills are foundational for network reconnaissance and penetration testing.
