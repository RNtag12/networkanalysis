# Methods of network traversal
# Authors

- [@rntagashobotse](https://www.github.com/RNtag12)
- [@FrancisGomas](https://www.github.com/francisgomas)
  
# Project Description
This project demonstrates two methods of network traversal: port forwarding and VPN tunneling. The setup includes simulating a public and private network using VirtualBox and configuring DVWA (Damn Vulnerable Web Application) on an Ubuntu VM as the target host. The aim is to establish connections to the target machine from a Kali Linux VM, using a jump host in between for network traversal. This project explores SSH port forwarding and VPN tunneling to access the target, showcasing network interaction and vulnerability exploitation.

# Tools
- VirtualBox
- Ubuntu (Jump Host & Target)
- Kali Linux
- Apache Web Server
- DVWA
- OpenVPN
# Virtual machine setup
<img src="https://imgur.com/dQV4d8W.png" height="80%" width="80%" alt="VM setup"/> 
# Demonstration Goals
<u>Network Setup</u>: Simulate a public and private network using NAT Networks in VirtualBox. Display the IP addresses of the jump host and target Ubuntu machines.
DVWA Access: Show that DVWA is accessible locally from the target machine and via the jump host.
SSH Port Forwarding: Demonstrate SSH login from the Kali VM to the jump host and access the DVWA from Kali using port forwarding.
Command: ssh -L 8888:<target-host>:80 user@<jump-host> -N.
VPN Tunneling: Configure OpenVPN on the jump host to enable full network access from the Kali machine. Show successful VPN setup and access to DVWA via VPN from the Kali machine.

 # Visual demonstration
 - [Video_Demo](https://github.com/RNtag12/networkanalysis/blob/main/Week2_video_demo.zip)
