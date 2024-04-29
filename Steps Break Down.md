Breakdown of NTT-lab Project Steps:

1. Starting from Scratch:
<li>a. Commencing with a pre-configured WAN-Cloud and WAN-Switch in GNS3.</li>
<li>b. Adding a FortiGate firewall, two switches, and a Windows 10 workstation to the network.</li>
<li>c. Establishing network connections.</li>

3. Setting up a Virtual LAN Interface Using PuTTY:
<li>a. Access the CLI and enter "conf sys int."</li>
<li>b. Edit port2.</li>
<li> c. Configure access for ping, HTTP, HTTPS, and SSH.</li>
<li> d. Set the IP address to 10.128.0.1/24.</li>
<li> e. Exit configuration.</li>

4. Verifying the Configuration:
  <li> a. Confirm the configuration of port2 using "show sys int port2."</li>

4. Configuring the DHCP Server for the LAN Interface:
<li> a. Access the CLI and enter "conf sys dhcp server."</li>
<li>  b. Edit the DHCP server settings.</li>
<li>  c. Set the default gateway to 10.128.0.1.</li>
<li>  d. Configure the subnet mask as 255.255.255.0.</li>
<li>  e. Assign the interface to port2.</li>
<li> f. Define the IP range.</li>
<li>  g. Specify the start and end IP addresses.</li>
 <li>  h. Exit configuration.</li>

5. Verifying the DHCP Server Configuration:
<li> a. Confirm the DHCP server settings using "show sys dhcp server 1."</li>

6. Setting Up a Windows 10 Workstation and Verifying DHCP Lease:
<li> a. Use the "ipconfig /all" command on the workstation.</li>
<li>b. Verify:</li>
<li> - Valid IP range: 10.128.0.[100-199]/24</li>
<li> - Gateway: 10.128.0.1</li>
<li> - DHCP server: 10.128.0.1</li>

7. Testing Network Connectivity:
<li> a. Ping 10.128.0.1 (LAN) should succeed.</li>
<li> b. Ping 8.8.8.8 (WAN) should fail.</li>
<li>c. Ping google.com (DNS) should fail.</li>

8. Accessing the GUI via the Win10 Browser:
<li>a. Enter "http://10.128.0.1/" in the browser to access the login interface.</li>
<li>b. Log in with admin credentials used for the firewall CLI.</li>
<li>c. Select "later" when prompted to access the dashboard.</li>

9. Making System Changes on the Dashboard:
 <li>- Update hostname, timezone, enable local NTP server, list interfaces, set idle timeout, and enable auto file system check.</li>

10. Backup the Configuration.

11. Reboot the Firewall.

12. Completing Network Setup:
 <li>a. Configure network interfaces for LAN, Guest, and DMZ networks.</li>
 <li>b. Edit port1 (WAN), port2 (LAN), port3 (GUEST), port4 (DMZ).</li>

13. Enabling and Configuring DNS:
 <li>a. Enable DNS in "system > Feature visibility."</li>
 <li>b. Configure DNS firewall settings in "Network > DNS."</li>

14. Configuring Network DNS Servers:
<li>a. Set up LAN DNS.</li>
<li>b. Configure GUEST DNS.</li>
<li>c. Define DMZ DNS.</li>

15. Creating Service Objects:
<li>a. Define LAN services in a service group.</li>
<li>b. Define DMZ services in a service group.</li>

16. Configuring Firewall Rules:
<li>   a. LAN-to-WAN policy.</li>
<li>   b. DMZ-to-WAN policy.</li>
<li>   c. LAN-to-DMZ policy.</li>
<li> d. DMZ-to-LAN policy.</li>
<li> e. WAN-to-DMZ policy.</li>

17. Backup the Firewall Configuration.
