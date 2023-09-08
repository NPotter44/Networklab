# Hardening Research Notes

#### Notes on hardening go here.

Hardening a FortiGate firewall.
Using password policies such as character requirements password reuse and expiration, and login failure lockout to log into fortigate. Make sure it is in a physically secure location. Keep firmware up to date and use encrypted protocols. Back up the Fortigate configuration. Be sure to enable encryption when backing up the configuration, store the configuration file in a secure location, delete old configuration files that are no longer needed. Take precautions against Denial of service attack by, enabling DoS policies to incoming traffic. These include looking for anomalous traffic patterns, ensuring Fortigate is receving regular IPS signature updates from the FortiGuard network, adjust traffic rates if a traffic pattern has already been established.

Source: https://docs.fortinet.com/document/fortigate/7.2.0/best-practices/555436/hardening

Hardening Windows 10.
Ensure you are doing a secure installation while disconnected from the internet. Get rid of any unwanted programs. Use encryption tools like Bitlocker as well as secure boot. Keep Windows 10 system up to date on all updates, patches, and service packs. Enable built in OS guards. Utilize complex passwords with a reset interval with no reuse, and multifactor authentication. Secure web browsing.

Source: https://techcommunity.microsoft.com/t5/windows-security/hardening-windows-10-on-an-it-pro-s-latptop/m-p/180502

Hardening Windows Server 2012r2.
Ensure you are doing a secure installation while disconnected from the internet until operating system is installed and hardened. Keep up to date on updates, service packs and hotfixes; best done through automatic notification. Configure User account policies, password, and lockout policy. Restrict access from the network to administrators and authenticated users. Configure Event log settings, account log on, audit, and management policies. Ensure Network Access Controls and Network Security settings are configured correctly. Nothing should be allowed to accessed anonymously. Firewall should be configured in Domain, Private and Public.

Source: https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/defending-windows-server-2012-r2-and-2016/ba-p/2783292

Hardening Ubuntu Server 18.04
Keeping system up to date. Create a non-root user with sudo privileges. Make a habit of logging into your Ubuntu 18.04 server using a non-root account. Use authentication Key pair to log to your server. Using a private/public key is considered safe because the keys are tough to guess. Disallow SSH password authentication. Disable remote root login. Whitelist users. We can limit the users that are allowed to log in SSH. Multi-Factor Authentication. Although this is not a conclusive list of all security tools and configurations that you should have on your Ubuntu 18.04 server, I hope you have found this useful and your server will now be just a bit more hard to break into.
Source: https://ubuntu.com/blog/national-cyber-security-centre-pub
