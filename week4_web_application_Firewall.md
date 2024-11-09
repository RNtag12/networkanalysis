# Web Application Firewall Setup with NAXSI and NGINX

# Authors
- [@rntagashobotse](https://www.github.com/RNtag12)
- [@FrancisGomas](https://www.github.com/francisgomas)

# Project Description
This project demonstrates how to set up a web application firewall (WAF) to filter potential malicious HTTP requests targeting a web server. Unlike a traditional network-layer firewall (e.g., Snort), the WAF in this lab operates at the application layer using NAXSI with NGINX as the web server. We will also configure the Damn Vulnerable Web Application (DVWA) with PHP-FPM and set NAXSI to detect and block attacks, including SQL injection (SQLi) and cross-site scripting (XSS) attempts.  

# Tools
- VirtualBox
- Kali Linux (Penetration Testing VM)

# Security tools
- NGINX (Web Server)
- NAXSI (Web Application Firewall)
- PHP-FPM (FastCGI Process Manager for PHP)
- DVWA (Damn Vulnerable Web Application)
  
# Demonstration goals
- Host DVWA using NGINX with PHP-FPM integration and confirm that NGINX and NAXSI are configured correctly and blocking malicious requests
- Compile and configure NAXSI as a WAF to filter incoming requests and verify access to DVWA and the functionality of XSS and SQLi attack blocking.
- Show evidence of successful rule modifications by allowing legitimate requests in LearningMode.
  
# Required setups and installations
## VirtualBox Configuration

- Setup Ubuntu with NAT Network
- Use Ubuntu 19.04 (pre-configured for NAXSI) with NAT settings.
- Create a NAT network for Ubuntu and Kali Linux instances to simulate a secure network environment.
- Configure port forwarding to allow access to DVWA via the host machine.

## Network credentials:
- Change Network Adapter
- Switch the network adapter to a "Host-only Adapter" to prevent DVWA from being accessible to other networks, ensuring the environment remains isolated.
- Setting Up NGINX with NAXSI
  
## Required installation:
- Download and compile NGINX with the NAXSI plugin following online guides, such as DigitalOcean's NAXSI tutorial.
- Test HTTP requests to verify that NAXSI is filtering requests and logging blocked actions in /var/log/nginx/error.log.
- PHP and PHP-FPM Installation
- Install PHP and PHP-FPM as NGINX does not support PHP natively.
- Configure FastCGI for PHP using PHP-FPM (refer to php-fpm.org for setup details).
- Ensure the directories /etc/nginx/sites-available and /etc/nginx/sites-enabled are created, and configure symbolic links if necessary.

## Configuring NGINX for DVWA
- Configure NGINX to Point to DVWA
- Update the default file in /etc/nginx/sites-available to point NGINX to DVWA, ensuring correct PHP and MySQL integration.
- Verify DVWA accessibility by loading login.php in a browser and logging in with admin/password.

 # Visual demonstration
 - [Video_Demo](https://github.com/RNtag12/networkanalysis/blob/main/Week4_Video_demo.zip)
 

