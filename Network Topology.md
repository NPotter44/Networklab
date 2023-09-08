This wiki will be used to document the network resources for the Widgets environment.

<html>
 <style>
  ul.nobullet {
   list-style-type:none;
   }
 </style>
<body>

Firewall 
hostname = firewall 
FQDN = firewall.widget.localdomain a-record created = static on dc.widgets.localdomain 
 <ul class="nobullet">
  <li>network info: </li>
  <li> wan is port1 on dhcp from cloud, connected to WAN-SWITCH </li> 
  <li> lan is port2 on 10.128.0.1/24, connected to LAN-SWITCH </li>  
  <li> dmz is port4 on 10.128.10.1/24, connected to DMZ-SWITCH </li> 
  <li> guest is port3 on 10.128.99.1/24,  not connected </li>
</ul>

win10 hostname = win10 FQDN = dc.widgets.localdomain a-record created = dynamically on dc.widgets.localdomain network info: dhcp, LAN network

dc hostname = dc FQDN = dc.widgets.localdomain a-record created = automatically on dc.widgets.localdomain network info: static, 10.128.0.10/24 services: AD and DNS services

iis hostname = iis FQDN = iis.widgets.localdomain a-record created = dynamically on dc.widgets.localdomain network infor: static, 10.128.0.80/24, LAN network services: webserver

www hostname = www FQDN = www.widgets.localdomain a-record created = static on dc.widgets.localdomain network info: static, 10.128.10.80/24, DMZ network services: webserver, wiki
</html>
<body>
