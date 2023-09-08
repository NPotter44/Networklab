# Network resources for the Widgets environment.

<html>
 <body>
 
 # Firewall
  <p> Hostname = firewall </p> 
  <p> FQDN = firewall.widget.localdomain </p>
  <p> a-record created = static on dc.widgets.localdomain </p> 
  <b> Network info </b>
  <p> &nbsp&nbsp&nbsp&nbsp&nbsp wan is port1 on dhcp from cloud, connected to WAN-SWITCH </p> 
  <p> &nbsp&nbsp&nbsp&nbsp&nbsp lan is port2 on 10.128.0.1/24, connected to LAN-SWITCH </p>  
  <p> &nbsp&nbsp&nbsp&nbsp&nbsp dmz is port4 on 10.128.10.1/24, connected to DMZ-SWITCH </p> 
  <p> &nbsp&nbsp&nbsp&nbsp&nbsp guest is port3 on 10.128.99.1/24,  not connected </p>

 # WIN10
  <p> Hostname = win10 </p> 
  <p> FQDN = dc.widgets.localdomain </p>
  <p> a-record created = dynamically on dc.widgets.localdomain </p> 
  <b> Network info </b> 
  <p> &nbsp&nbsp&nbsp&nbsp&nbsp dhcp, LAN network </p>

# DC
  <p> Hostname = dc </p>
  <p> FQDN = dc.widgets.localdomain </p>
  <p> a-record created = automatically on dc.widgets.localdomain </p> 
  <b> Network info </b>
  <p>  &nbsp&nbsp&nbsp&nbsp&nbsp static, 10.128.0.10/24 </p> 
  <p>  &nbsp&nbsp&nbsp&nbsp&nbsp services: AD and DNS services </p>

# iis 
  <p> Hostname = iis </p>
  <p> FQDN = iis.widgets.localdomain </p>
  <p> a-record created = dynamically on dc.widgets.localdomain </p>
  <b> </b>Network info </b>
  <p>  &nbsp&nbsp&nbsp&nbsp&nbsp static, 10.128.0.80/24, LAN network </p> 
  <p>  &nbsp&nbsp&nbsp&nbsp&nbsp services: webserver </p>

# www 
  <p> Hostname = www </p>
  <p> FQDN = www.widgets.localdomain </p>
  <p> a-record created = static on dc.widgets.localdomain </p>
  <b> Network info </b> 
  <p> &nbsp&nbsp&nbsp&nbsp&nbsp static, 10.128.10.80/24, DMZ network </p> 
  <p> &nbsp&nbsp&nbsp&nbsp&nbsp services: webserver, wiki </p>

 </body>
</html>
<p></p>
<p></p>

# Network Topology Diagram
![image](https://github.com/NPotter44/Networklab/assets/144384452/2ff0ace1-ee65-4601-bb0d-bc07fb8f61d5)

