# Networklab
Welcome to the widget.localdomain Wiki

Hardening Research Notes

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
Source: https://ubuntu.com/blog/national-cyber-security-centre-publish-ubuntu-18-04-lts-security-guide


This wiki will be used to document the network resources for the Widgets environment.

firewall
  hostname = firewall
  FQDN = firewall.widget.localdomain 
  a-record created = static on dc.widgets.localdomain
  network info:
    wan is port1 on dhcp from cloud, connected to WAN-SWITCH
    lan is port2 on 10.128.0.1/24, connected to LAN-SWITCH
    dmz is port4 on 10.128.10.1/24, connected to DMZ-SWITCH
    guest is port3 on 10.128.99.1/24, not connected

win10
  hostname = win10
  FQDN = dc.widgets.localdomain
  a-record created = dynamically on dc.widgets.localdomain
  network info: dhcp, LAN network

dc
  hostname = dc
  FQDN = dc.widgets.localdomain
  a-record created = automatically on dc.widgets.localdomain
  network info: static, 10.128.0.10/24
  services: AD and DNS services

iis
  hostname = iis
  FQDN = iis.widgets.localdomain
  a-record created = dynamically on dc.widgets.localdomain
  network infor: static, 10.128.0.80/24, LAN network
  services: webserver

www
  hostname = www
  FQDN = www.widgets.localdomain
  a-record created = static on dc.widgets.localdomain
  network info: static, 10.128.10.80/24, DMZ network
  services: webserver, wiki

![image](https://github.com/NPotter44/Networklab/assets/144384452/8a895fa2-7f04-408b-8ab6-74bfce7fe5b7)

 

Greenbone Scan Results


Vulnerabilities


SSL/TLS: Deprecated SSLv2 SSLv3 Protocol detection
* Summary: It was possible to detect the usage of the deprecated SSLv2 and/or SSLv3 protocol on the system.
* Impact: An attacker might be able to use the known cryptographic flaws to eavesdrop the connection between clients and the service to get access to sensitive data transferred within the secured connection. Furthermore newly uncovered vulnerabilities in this protocols won't receive security updates anymore.
* Solution: Solution Type Mitigation- It is recommended to disable the deprecated SSLv2 and/or SSLv3 protocols in favor of the TLSv1.2+ protocols. Please see the references for more information.


Weak(small) Public Key size(s)(ssh)
* Summary: The remote SSH server uses a weak (too small) public key size.
* Impact: A man-in-the-middle attacker can exploit this vulnerability to record the communication to decrypt the session key and even the messages.
* Solution: Solution Type Mitigation- -⇐1024 bit 4 RSA based keys: Install a RSA public key length of 2048 bits or greater, or to switch to more secure key types.


SSL/TLS: Server certificate/certificate in chain with RSA keys less than 2048 bits
* Summary: The remote SSL/TLS server certificate and/or any of the certificates in the certificate chain is using an RSA key with less than 2048 bits.
*Impact: Using certificates with weak RSA key size can lead to unauthorized exposure of sensitive information.
* Solution: Solution Type Mitigation- Replace the certificate with a stronger key and reissue the certificates it signed.


SSL/TLS: Server certificate/certificate in chain with RSA keys less than 1024 bits
* Summary: The remote SSL/TLS server certificate and/or any of the certificates in the certificate chain is using a RSA key with less than 1024 bits.
*Impact: Using certificates with weak RSA key size can lead to unauthorized exposure of sensitive information.
* Solution: Solution Type Mitigation- Replace the certificate with a stronger key and reissue the certificates it signed.


Weak Key exchange (KEX) algorithm(s) supported (SSH)
* Summary: The remote SSH server is configured to allow / support weak key exchange (KEX) algorithm(s).
*Impact: An attack can quickly break individual connections.
* Solution: Solution Type Mitigation- Disable the recorded weak KEX algorithm(s). 1024-bit MOTP group / prime KEX algorithms: Alternatively use elliptic-curve Diffie-Hellmann in general, e.g.Curve 25519.



SSL/TLS: Report Weak Cipher Suites
* Summary: This routine reports all Weak SSL/TLS cipher suites accepted by a service.
* No Impact
* Solution: Solution Type Mitigation- The configuration of this services should be changed so that it does not accept the listed weak cipher suites anymore.


SSL/TLS: Report Null Cipher Suites
* Summary: This routine reports all “Null” SSL/TLS cipher suites accepted by a service.
* Impact: This could allow remote attackers to obtain sensitive information or have other, unspecified impacts.
* Solution: Solution Type Mitigation- The configuration of this services should be changed so that it does not accept the listed “Null” cipher suites anymore.
Please see the references for more resources supporting you in this task.


SSL/TLS: RSA Temporary Key Handling 'RSA_EXPORT' Downgrade Issue (FREAK)
* Summary: This host is accepting 'RSA_EXPORT' cipher suites and is prone to man in the middle atatck.
* Impact: Successful exploitation will allow remote attacker to downgrade the security of a session to use “RSA_EXPORT' cipher suites, which are significantly weaker than non-export cipher suites. This may allow a man-in-the-middle attacker to more easily break the encryption and monitor or tamper with the encrypted stream.
* Solution: Solution Type Vendorfix -Remove Support for 'RSA_EXPORT' cipher suites from the service.
Edit
Weak Encryption Algorithm(s) Supported (SSH)
Summary: The remote SSH server is configured to allot / support weak encryption algorithm(s).
No impact
Solution: Solution Type: Mitigation
Disable the reported weak encryption algorithm(s).
Edit

SSL/TLS: 'DHE_EXPORT' Man In The Middle Security Bypass Vulnerability (LogJam)
Summary: This host is accepting 'DHE_EXPORT' cipher suites and is prone to man in the middle attack.
Impact: Successful exploitation will allow a man-in-the-middle attacker to downgrade the security of a TLS session to 512-bit export-grade cryptography, which is significantly weaker, allowing the attacker to more easily break the encryption and monitor or tamper with the encrypted stream.
Solution: Solution Type Vendorfix
Remove support for the “DHE_EXPORT' cipher suites from the service.
If running OpenSSL updateto version 1.0.2b or 1.0.1n or later.
Edit

SSL/TLS: SSLv3 Protocol CBC Cipher Suites Information Disclosure Vulnerability (POODLE)
Summary: This host is prone to an information disclosure vulnerability.
Impact: Successful exploitation will allow a man-in-the-middle attackers gain access to the plain text data stream.
Solution: Solution Type: Mitigation
Possible Mitigations are:
Disable SSLv3
Disable cipher suites supporting CBC cipher modes
Enable TLS_FALLBACK_SCSV if the service is providing TLSv1.0+
Edit

TCP Timestamps Information Disclosure
Summary: The remote host implements TCP timestamps and therefore allows to compute the uptime.
Impact: A side effect of this feature is that the uptime of the remote host can sometimes be computed.
Solution: Solution Type: Mitigation
To disable TCP timestamps on Linux add the line 'net.ipv4.tcp_timestamps = 0' to /etc/systctl.conf. Execute 'sysctl -p' to apply the settings at runtime.
To disable TCP timestamps on Windows execute 'netsh int tcp set global timestamps=disabled'
Starting with Windows Server 2008 and Vista, the timestamp can not be completely disabled.
The default behavior of the TCP/IP stack on this Systems is to not use the Timestamp options when initiating TCP connections, but use them if the TCP peer that is initiating communication includes them in their synchronize (SYN) segment.
See the references for more information.
Edit

Weak MAC Algorithm(s) Supported (SSH)
Summary: The remote SSH server is configured to allow / support weak MAC algorithm(s).
No Impact
Solution: Solution Type: Mitigation
Disable the reported weak MAC algorithm(s).

