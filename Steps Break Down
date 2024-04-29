Breakdown of NTT-lab Project Steps:

1. Starting from Scratch:
   a. Commencing with a pre-configured WAN-Cloud and WAN-Switch in GNS3.
   b. Adding a FortiGate firewall, two switches, and a Windows 10 workstation to the network.
   c. Establishing network connections.

3. Setting up a Virtual LAN Interface Using PuTTY:
   a. Access the CLI and enter "conf sys int."
   b. Edit port2.
   c. Configure access for ping, HTTP, HTTPS, and SSH.
   d. Set the IP address to 10.128.0.1/24.
   e. Exit configuration.

4. Verifying the Configuration:
   a. Confirm the configuration of port2 using "show sys int port2."

4. Configuring the DHCP Server for the LAN Interface:
   a. Access the CLI and enter "conf sys dhcp server."
   b. Edit the DHCP server settings.
   c. Set the default gateway to 10.128.0.1.
   d. Configure the subnet mask as 255.255.255.0.
   e. Assign the interface to port2.
   f. Define the IP range.
   g. Specify the start and end IP addresses.
   h. Exit configuration.

5. Verifying the DHCP Server Configuration:
   a. Confirm the DHCP server settings using "show sys dhcp server 1."

6. Setting Up a Windows 10 Workstation and Verifying DHCP Lease:
   a. Use the "ipconfig /all" command on the workstation.
   b. Verify:
      - Valid IP range: 10.128.0.[100-199]/24
      - Gateway: 10.128.0.1
      - DHCP server: 10.128.0.1

7. Testing Network Connectivity:
   a. Ping 10.128.0.1 (LAN) should succeed.
   b. Ping 8.8.8.8 (WAN) should fail.
   c. Ping google.com (DNS) should fail.

8. Accessing the GUI via the Win10 Browser:
   a. Enter "http://10.128.0.1/" in the browser to access the login interface.
   b. Log in with admin credentials used for the firewall CLI.
   c. Select "later" when prompted to access the dashboard.

9. Making System Changes on the Dashboard:
   - Update hostname, timezone, enable local NTP server, list interfaces, set idle timeout, and enable auto file system check.

10. Backup the Configuration.

11. Reboot the Firewall.

12. Completing Network Setup:
   a. Configure network interfaces for LAN, Guest, and DMZ networks.
   b. Edit port1 (WAN), port2 (LAN), port3 (GUEST), port4 (DMZ).

13. Enabling and Configuring DNS:
   a. Enable DNS in "system > Feature visibility."
   b. Configure DNS firewall settings in "Network > DNS."

14. Configuring Network DNS Servers:
   a. Set up LAN DNS.
   b. Configure GUEST DNS.
   c. Define DMZ DNS.

15. Creating Service Objects:
   a. Define LAN services in a service group.
   b. Define DMZ services in a service group.

16. Configuring Firewall Rules:
   a. LAN-to-WAN policy.
   b. DMZ-to-WAN policy.
   c. LAN-to-DMZ policy.
   d. DMZ-to-LAN policy.
   e. WAN-to-DMZ policy.

17. Backup the Firewall Configuration.
