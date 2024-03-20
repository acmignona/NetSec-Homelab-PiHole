# NetSec-Homelab-PiHole
Quick writeup regarding my experience installing and configuring PiHole, a DNS sinkhole, within my homelab. There are other great resources that you can also use else where to emulate this project. 

![PI](https://github.com/acmignona/NetSec-Homelab-PiHole/assets/81653524/2fde8aa5-94b8-48c4-9f46-9f5e9fba2787)

## Requirements: 

## Installing and Configuring Pi-Hole on Raspberry Pi with DietPi OS
Pi-Hole is a powerful network-wide ad blocker that runs on Raspberry Pi, making your entire network ad-free. This high-level guide will walk through the process of installing and configuring Pi-Hole on a Raspberry Pi with the DietPi operating system. We'll assume you've already set up your Raspberry Pi and it has a static local IP address of 192.168.1.203.

## Prerequisites:
- A Raspberry Pi (any model should work). (This can be any model. I bought mine from Amazon: https://a.co/d/6qQ4fvL)
- DietPi OS installed and configured on your Raspberry Pi. (Mr Steve on Youtube has a fanastic guide on this: https://www.youtube.com/watch?v=RO2_eZlVrj4)
- A static local IP address assigned to your Raspberry Pi.

### Step 1: Connect to Your Raspberry Pi
You can access your Raspberry Pi through SSH from your computer. Open a terminal or command prompt on your computer and run:

`ssh dietpi@192.168.1.203`
Replace 192.168.1.203 with the IP address of your Raspberry Pi.

### Step 2: Install Pi-Hole
Once you've logged in to your Raspberry Pi, you can begin the installation of Pi-Hole. Run the following command:

`curl -sSL https://install.pi-hole.net | bash`  (https://docs.pi-hole.net/main/basic-install/)

This command will download and run the Pi-Hole installation script. Follow the on-screen instructions to configure Pi-Hole. When asked to select the upstream DNS provider, you can choose your preferred option (e.g., Google, OpenDNS, or Custom).

### Step 3: Set Up Your Router
For Pi-Hole to work effectively, you need to configure your router to use the Raspberry Pi's IP address (192.168.1.203) as the DNS server for your network. Access your router's settings through a web browser and find the DNS settings. Set the primary DNS server to 192.168.1.203 (as shown below in my Netgear Router's web interface).

![image](https://github.com/Vuitton-Toine/NetSec-Homelab-PiHole/assets/81653524/66b76097-c0ef-4e3a-8fbe-44620dfc29ea)

#### Alternative - Windows Host Manual DNS Configuration 

![image](https://github.com/Vuitton-Toine/NetSec-Homelab-PiHole/assets/81653524/cc37128b-fc3a-46ce-9cbc-4bb8626fd550)

#### Alternative - Linux Host Manual DNS Configuration

Run `sudo nmtui`. Select **edit a Connection**. Select your connection > edit.    

Set IPv4 configuration to Manual. Add DNS. Enter in PiHole IPv4 address.

Disable then reactivae the connection. Quit. 

### Step 4: Configure Pi-Hole
To access the Pi-Hole web interface and configure it further, open a web browser and enter your Raspberry Pi's IP address followed by "/admin" (e.g., http://192.168.1.203/admin/). You'll be presented with the Pi-Hole dashboard, where you can manage settings, view statistics, and add custom blocklists.


