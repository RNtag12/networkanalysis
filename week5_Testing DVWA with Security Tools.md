# Web Application Vulnerability Testing
# Authors
- [@rntagashobotse](https://www.github.com/RNtag12)
- [@FrancisGomas](https://www.github.com/francisgomas)

# Project Description
This project explores the process of testing web application vulnerabilities using the Damn Vulnerable Web Application (DVWA) as a testbed. Students will employ security tools to assess the application's weaknesses, focusing on brute-force attacks, SQL injection (SQLi), and XSS vulnerabilities.

# Tools
Kali Linux Tools:
- Nmap
- Dirb
- DirBuster
- Gobuster
- Burp Suite
- SQLMap

# Objectives
- Demonstrate vulnerability assessment of DVWA using automated tools.
- Simulate and analyze brute-force attacks on low-security DVWA settings.
- Exploit SQLi vulnerabilities using SQLMap.
# Setup and Installation
Virtual Environment Configuration
Setting Up DVWA:
Install DVWA following guidelines on AskUbuntu.
Integrate DVWA with MySQL and PHP.
# Networking
- Configure VirtualBox to isolate the DVWA server.
- Security Tools Integration
# Tools used
- <b>Nmap </b> for Network Scanning: Perform scans to enumerate open ports and services on the DVWA host.
- <b>Dirb and DirBuster</b> for Directory Enumeration: Identify hidden directories or files in the DVWA structure.
  - Gobuster: Use wordlists to enhance enumeration efficiency.
Brute-Force Testing
Burp Suite for :Conduct brute-force attacks on DVWA's login interface in low-security mode.
Refer to the tutorial on brute-force attacks.
SQL Injection
SQLMap:Exploit DVWA SQLi vulnerabilities using the tool's automated techniques.
Refer to the SQLMap documentation for advanced exploitation methods.
Goals and Validation
Attack Simulations: Execute common web attacks, such as SQLi and XSS, using tools in Kali Linux.
Risk Mitigation: Understand defensive mechanisms and mitigation strategies based on observed vulnerabilities.
Resources

