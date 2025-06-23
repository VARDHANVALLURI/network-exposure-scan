My Journey: Cybersecurity Internship - Task 1 (Scanning My Local Network)
Hello and Welcome!
Process:
Install Nmap. 
Find your local IP range (e.g., 192.168.1.0/24). 
Perform a TCP SYN scan using nmap -sS [your IP range]. 
Note down found IP addresses and open ports. 
Optionally, analyze packet capture with Wireshark. 
Research common services running on those ports. 
Identify potential security risks from open ports. 
Save scan results as a text or HTML file. 
Outcome: The task aims us to know basic network reconnaissance skills and an understanding of network service exposure. 

What My Scan Found:
My network scan identified two active hosts:

192.168.25.221: Port 53/tcp (domain) open, used for DNS.
192.168.25.35: Ports 135/tcp (msrpc), 139/tcp (netbios-ssn), and 445/tcp (microsoft-ds) open, typically for Windows inter-process communication and file sharing (SMB). Full details are in nmap_scan_results.txt.

Potential Security Risks:

These open ports present security concerns:

Port 53 (DNS): Risk of cache poisoning or amplification if misconfigured.
Ports 135, 139, 445 (MSRPC, NetBIOS, SMB): Common Windows targets. Unpatched SMB (port 445) can lead to critical exploits like "EternalBlue," allowing unauthorized access and data compromise. They can also reveal system information. Securing these requires constant patching, proper configuration, and strong authentication.

What's Inside This Repository

README.md: This file.
nmap_scan_results.txt: Full Nmap scan output 
single_host_scan.png: Initial Nmap scan screenshot.
network_range_scan.png: Full network range Nmap scan screenshot.
