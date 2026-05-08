# STP

# Network Topology
<img width="451" height="341" alt="image" src="https://github.com/user-attachments/assets/5d831eec-a75d-4466-b1f0-9c474a84f041" />

STP (Spanning Tree Protocol) is a layer 2 service that permits and denies redundant links. This effectively prevents broadcast storms and MAC address table instability. A broadcast storm is when devices forward broadcast packets to each other in a loop until the network crashes due to intense hardware use. A MAC address table is kept on each switch so that they know where traffic should be sent. Switches only forward traffic based on MAC addresses.

### Devices Used:
- Cisco IOSvL2 15.2.1 switch
- GNS3 Software
- Ubuntu Container (running on VMware machine)


## Configurations

| R1 | Column 2 | Column 3 |
|----------|----------|----------|
| enable
conf t
host switch1
int vlan2
ip address 192.168.2.30 255.255.255.0 
no shut
end


conf t
vlan 2
name General
end


conf t
username msfadmin password msfadmin
enable password msfadmin
line vty 0 4
login local
transport input all
end


conf t
username msfadmin pass msfadmin
username msfadmin priv 15

line vty 0 4
login local
transport input all

ip domain-name example.com
crypto key generate rsa
1024

end
wr | Row 1 B  | Row 1 C  |
| Row 2 A  | Row 2 B  | Row 2 C  |
```
Yikes
```
