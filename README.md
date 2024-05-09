# Kopanomothlaka-Virtual-router-running-Ubuntu
Virtual router running Ubuntu

# Setting up a Virtual Router Running Ubuntu

This repository contains a comprehensive guide on setting up a virtual router running Ubuntu to facilitate communication between PCA and PCB. It covers Network Address Translation (NAT), Dynamic Host Control Protocol (DHCP), firewall setup, and basic routing functionalities.

## Comprehensive Report

### Introduction
This work describes how to set up a virtual router running Ubuntu to facilitate communication between PCA and PCB. Network Address Translation (NAT), Dynamic Host Control Protocol (DHCP), firewall, and basic routing functionalities will all be configured under the. The network interfaces enp0s3, enp0s8, and enp0s9 are utilized for this. I designed the router and the clients using Ubuntu and Oracle Virtual Machines.

### Tools Used
- **Linux Distribution:** Ubuntu Server sourced from the official Ubuntu website.
- **Virtualization Platform:** Oracle VM VirtualBox sourced from the official VirtualBox website.

### Installation Steps
0. **Oracle VM VirtualBox Installation:**
   - Download Oracle VM VirtualBox from [here](https://www.virtualbox.org) and follow the installation instructions for your operating system.
   - Launch VirtualBox after installation.

1. **Ubuntu Server Installation:**
   - Create a new virtual machine in VirtualBox.
   - Allocate resources (RAM, disk space) and select Ubuntu Server (64-bit) as the guest OS.
   - Install Ubuntu Server using the ISO file downloaded from [Ubuntu's official website](https://ubuntu.com/download/server).
   - Configure language, keyboard layout, network settings, root password, and user account during installation.

### Configuration Steps
2. **Network Configuration:**
   - Add network adapters in VirtualBox settings for external network (NAT) and internal communication (Internal Network).
   - Enable IP forwarding, configure NAT using iptables, set up DHCP, and define firewall rules.
   - Install OpenSSH server for remote access if needed.

3. **IP Forwarding:**
   - Open the terminal for the router to allow IP forwarding.
   - Edit `sysctl.conf` file using a text editor (e.g., nano).
   - Uncomment the line `net.ipv4.ip_forward=1` to enable IP forwarding.
   - Apply the changes by running: `sudo sysctl -p`

4. **NAT Configuration:**
   - Open the terminal for the Ubuntu Server virtual machine.
   - Update package lists and install iptables.
   - Create a new iptables rule for NAT and save it to persist across reboots.

5. **DHCP Setup:**
   - Update package lists and install the `isc-dhcp-server` package.
   - Edit `dhcpd.conf` file to define DHCP settings.
   - Start and enable the DHCP server service.

### Firewall Configuration
- Set up firewall rules using iptables to allow/block traffic as per your network security requirements.
- Define rules for inbound and outbound traffic, ensuring necessary services are accessible while unauthorized access is blocked.

### SSH Configuration
- Install SSH (`openssh-server`) for remote access.

### Ping
- Test communication using ping.

### Challenges and Lessons Learned
- Network Interface Configuration: Misconfiguration and compatibility issues.
- Firewall Configuration: Rule conflicts, specificity, and dynamic environments.
- Troubleshooting: Debugging network issues required patience and attention to detail.

For detailed instructions and the complete setup guide, refer to the comprehensive report included in this repository.

---


