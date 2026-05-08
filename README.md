# STP

# Network Topology
<img width="451" height="341" alt="image" src="https://github.com/user-attachments/assets/5d831eec-a75d-4466-b1f0-9c474a84f041" />

STP (Spanning Tree Protocol) is a layer 2 service that permits and denies redundant links. This effectively prevents broadcast storms and MAC address table instability. A broadcast storm is when devices forward broadcast packets to each other in a loop until the network crashes due to intense hardware use. A MAC address table is kept on each switch so that they know where traffic should be sent. Switches only forward traffic based on MAC addresses.

### Devices Used:
- Cisco IOSvL2 15.2.1 switch
- GNS3 Software
- Ubuntu Container (running on VMware machine)


## Configurations

| Switch 1 | Switch 2 | Switch 3 | Switch 4 |
|----------|----------|----------|----------|
| enable<br>conf t<br>host switch1<br>int vlan2<br>ip address 192.168.2.30 255.255.255.0<br>no shut<br>end<br><br>conf t<br>vlan 2<br>name General<br>end | enable<br>conf t<br>host switch1<br>int vlan2<br>ip address 192.168.2.30 255.255.255.0<br>no shut<br>end<br><br>conf t<br>vlan 2<br>name General<br>end | enable<br>conf t<br>host switch1<br>int vlan2<br>ip address 192.168.2.30 255.255.255.0<br>no shut<br>end<br><br>conf t<br>vlan 2<br>name General<br>end | enable<br>conf t<br>host switch1<br>int vlan2<br>ip address 192.168.2.30 255.255.255.0<br>no shut<br>end<br><br>conf t<br>vlan 2<br>name General<br>end |
