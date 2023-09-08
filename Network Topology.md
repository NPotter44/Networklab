This wiki will be used to document the network resources for the Widgets environment.

<html>
<body>

 # Firewall
 ## Network info
<p> Hostname = firewall </p> 
<p> FQDN = firewall.widget.localdomain a-record created = static on dc.widgets.localdomain </p> 

  <p> &nbsp&nbsp&nbsp&nbsp&nbsp wan is port1 on dhcp from cloud, connected to WAN-SWITCH </p> 
  <p> &nbsp&nbsp&nbsp&nbsp&nbsp lan is port2 on 10.128.0.1/24, connected to LAN-SWITCH </p>  
  <p> &nbsp&nbsp&nbsp&nbsp&nbsp dmz is port4 on 10.128.10.1/24, connected to DMZ-SWITCH </p> 
  <p> &nbsp&nbsp&nbsp&nbsp&nbsp guest is port3 on 10.128.99.1/24,  not connected </p>

win10 hostname = win10 FQDN = dc.widgets.localdomain a-record created = dynamically on dc.widgets.localdomain network info: dhcp, LAN network

dc hostname = dc FQDN = dc.widgets.localdomain a-record created = automatically on dc.widgets.localdomain network info: static, 10.128.0.10/24 services: AD and DNS services

iis hostname = iis FQDN = iis.widgets.localdomain a-record created = dynamically on dc.widgets.localdomain network infor: static, 10.128.0.80/24, LAN network services: webserver

www hostname = www FQDN = www.widgets.localdomain a-record created = static on dc.widgets.localdomain network info: static, 10.128.10.80/24, DMZ network services: webserver, wiki
</html>
<body>
