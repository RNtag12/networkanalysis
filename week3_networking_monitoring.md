# Network Configuration and Monitoring with pfSense and Snort

# Authors
- [@rntagashobotse](https://www.github.com/RNtag12)
- [@FrancisGomas](https://www.github.com/francisgomas)

# Project Description
This project demonstrates how to set up and monitor a corporate network using pfSense and Snort. The objective is to simulate network routing and packet analysis between different network segments, configuring pfSense as a firewall/router with multiple interfaces. Additionally, we will implement Snort as an Intrusion Detection System (IDS) to monitor traffic between the networks. The lab explores network setup, routing, and packet inspection between hosts using pfSense's network interfaces and monitoring tools.

# Tools
- VirtualBox
- Kali Linux (Penetration Testing VM)

# Security tools
- pfSense (Router & Firewall)
- Snort (Intrusion Detection System)
- DVWA (Damn Vulnerable Web Application)


      
# VirtualBox Configuration
## Configure two NAT networks in VirtualBox
- Developer Network (LAN): Subnet 192.168.56.0/24
- Server Network (OPT1): Subnet 10.0.2.0/24 (or another private subnet)
- Disable DHCP for both networks. DHCP will be managed by pfSense.
      - pfSense is configured with three network interfaces to simulate a public network for developers and a private network for servers, all controlled via pfSense:
    - WAN – Wide Area Network interface connected to the external network (bridged adapter).
    - LAN – Developer Network (Public NAT Network).
    - OPT1 – Server Network (Private NAT Network).

## Network Interface configurations
- WAN – Bridged adapter
- LAN – Connected to the Developer Network
- OPT1 – Connected to the Server Network.

# Setting up pfSense
## Terminal Configuration steps
### Assign Interfaces
- WAN for external access.
- LAN for the Developer Network.
- OPT1 for the Server Network.
### Configure IP Addresses and access pfSense Web Interface
- Assign the LAN IP address to 192.168.56.254 (Developer Network).
- Assign OPT1 with an appropriate static IP (e.g., 10.0.2.254 for the Server Network).
- Enable DHCP for both interfaces, configuring a range (e.g., 192.168.56.100 - 192.168.56.200 for LAN).
- Access pfSense Web Interface from a browser; navigate to 192.168.56.254 and log in using the credentials admin/pfsense.

## Web Configuration
### Configure the OPT1 Interface and firewall rules
- Enable the OPT1 interface and rename it to Server Network.
- Use a static IP for the interface (e.g., 10.0.2.254/24) and set the DHCP range for the Server network (e.g., 10.0.2.100 - 10.0.2.200).
- Create firewall rules to allow traffic between the LAN and Server network.
- Ensure proper routing between interfaces.
- Ensure DHCP is enabled on both LAN and Server interfaces.
- Assign a static IP address for the Server (DVWA).
  
## Setting Up Snort

### Interface configuration
- Navigate to System -> Package Manager and install Snort.
- Snort Interface Configuration:
    - Configure Snort on the Server Network (OPT1).
        - Under Rules, add a custom rule to detect ICMP traffic
        - Start Snort on the Server interface.

- Using Snort for Intrusion Detection

### Monitor and Blocking ICMP traffic
- From the Kali VM, ping the DVWA server.
- Use tcpdump on DVWA to capture the network packets
- Verify that the pings are captured in both Snort alerts and tcpdump.

### Blocking ICMP Traffic

Use pfSense's firewall rules to block ICMP traffic (ping) between the Developer Network (LAN) and the Server Network (OPT1).
Test the firewall by attempting to ping DVWA again and verifying that it is blocked.

## Demonstration goals
- Verify that pfSense is providing correct DHCP addresses for the Developer and Server Networks.
- Ensure that traffic can be monitored and controlled using Snort.
- Verify successful packet capture with tcpdump on DVWA.
- Show blocked ICMP traffic after applying firewall rules.
 # Visual demonstration
 - [Video_Demo](https://github.com/RNtag12/networkanalysis/blob/main/Week3_video_demo.zip)
  
