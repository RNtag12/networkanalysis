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
      



###

## Demonstration goals

 # Visual demonstration
 - [Video_Demo](https://github.com/RNtag12/networkanalysis/blob/main/Week4_Video_demo.zip)
 - 
  

Authors
@rntagashobotse
@FrancisGomas


Tools
VirtualBox
Kali Linux (Penetration Testing VM)
Security Tools
NGINX (Web Server)
NAXSI (Web Application Firewall)
PHP-FPM (FastCGI Process Manager for PHP)
DVWA (Damn Vulnerable Web Application)
VirtualBox Configuration
Setup Ubuntu with NAT Network
Use Ubuntu 19.04 (pre-configured for NAXSI) with NAT settings.
Create a NAT network for Ubuntu and Kali Linux instances to simulate a secure network environment.
Configure port forwarding to allow access to DVWA via the host machine.
Network credentials:
Username: ubuntu
Password: password
Change Network Adapter
Switch the network adapter to a "Host-only Adapter" to prevent DVWA from being accessible to other networks, ensuring the environment remains isolated.
Setting Up NGINX with NAXSI
Objective Overview
Host DVWA using NGINX with PHP-FPM integration.
Compile and configure NAXSI as a WAF to filter incoming requests.
Configure NGINX to serve DVWA and set up NAXSI rules to detect and block malicious requests.
NGINX and NAXSI Installation
Download and compile NGINX with the NAXSI plugin following online guides, such as DigitalOcean's NAXSI tutorial.
Test HTTP requests to verify that NAXSI is filtering requests and logging blocked actions in /var/log/nginx/error.log.
PHP and PHP-FPM Installation
Install PHP and PHP-FPM as NGINX does not support PHP natively.
Configure FastCGI for PHP using PHP-FPM (refer to php-fpm.org for setup details).
Ensure the directories /etc/nginx/sites-available and /etc/nginx/sites-enabled are created, and configure symbolic links if necessary.
Configuring NGINX for DVWA
Configure NGINX to Point to DVWA
Update the default file in /etc/nginx/sites-available to point NGINX to DVWA, ensuring correct PHP and MySQL integration.
Verify DVWA accessibility by loading login.php in a browser and logging in with admin/password.
NAXSI Configuration
Initial Setup
Start and stop services with:
bash
Copy code
sudo systemctl stop php7.*-fpm.service nginx
sudo systemctl start php7.1-fpm.service nginx
Configure NAXSI rules in naxsi.rules and ensure they are applied in the default NGINX site file.
Learning Mode
Enable NAXSI in “LearningMode” to allow monitoring of suspicious requests without blocking them.
Use error.log to observe which legitimate requests trigger NAXSI alerts and adjust rules to prevent false positives.
Attack Simulation on DVWA
XSS and SQL Injection (SQLi) Attacks
Cross-Site Scripting (XSS)
Launch a web browser on the Kali VM and open the DVWA interface.
Attempt an XSS attack in DVWA and observe NGINX’s /var/log/nginx/error.log for blocked actions.
Disable LearningMode in NAXSI, restart NGINX, and repeat the XSS attempt to observe the response.
SQL Injection (SQLi)
Attempt an SQLi attack on DVWA.
Observe the blocking behavior in NAXSI and error logs.
Enable LearningMode again for analysis.
Demonstration Goals
Confirm that NGINX and NAXSI are configured correctly and blocking malicious requests.
Verify access to DVWA and the functionality of XSS and SQLi attack blocking.
Show evidence of successful rule modifications by allowing legitimate requests in LearningMode.
Visual Demonstration
Create a screencast video showing:
Starting and stopping NGINX services.
Verifying PHP configuration via the browser.
Demonstrating blocked XSS and SQLi attacks in error.log.
Switching to LearningMode to observe the impact on request handling.
