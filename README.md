# STP

# Network Topology
<img width="451" height="341" alt="image" src="https://github.com/user-attachments/assets/5d831eec-a75d-4466-b1f0-9c474a84f041" />

STP (Spanning Tree Protocol) is a layer 2 service that permits and denies redundant links. This effectively prevents broadcast storms and MAC address table instability. A broadcast storm is when devices forward broadcast packets to each other in a loop until the network crashes due to intense hardware use. A MAC address table is kept on each switch so that they know where traffic should be sent. Switches only forward traffic based on MAC addresses.

This lab demonstrates how to set STP and watch the changes made automatically.

### Devices Used:
- Cisco IOSvL2 15.2.1 switch
- GNS3 Software
- Ubuntu Container (running on VMware machine)


## Configurations

__Note: The IP configurations are not necessary; they were a part of the lab that was not completed.__
| Switch 1 | Switch 2 | Switch 3 | Switch 4 |
|----------|----------|----------|----------|
| enable<br>conf t<br>host switch1<br>int vlan2<br>ip address 192.168.2.30 255.255.255.0<br>no shut<br>end<br><br>conf t<br>vlan 2<br>name General<br>end<br><br>conf t<br>interface range g0/0 - 3<br>switchport mode access<br>switchport access vlan 2<br>no shutdown<br>exit<br><br>no ip domain-lookup<br>spanning-tree mode pvst<br>spanning-tree vlan 2 priority 4096<br>end<br>wr | enable<br>conf t<br>host switch1<br>int vlan2<br>ip address 192.168.2.30 255.255.255.0<br>no shut<br>end<br><br>conf t<br>vlan 2<br>name General<br>end<br><br>conf t<br>interface range g0/0 - 3<br>switchport mode access<br>switchport access vlan 2<br>no shutdown<br>exit<br><br>no ip domain-lookup<br>spanning-tree mode pvst<br>spanning-tree vlan 2 priority 8192<br>end<br>wr | enable<br>conf t<br>host switch1<br>int vlan2<br>ip address 192.168.2.30 255.255.255.0<br>no shut<br>end<br><br>conf t<br>vlan 2<br>name General<br>end<br><br>conf t<br>interface range g0/0 - 3<br>switchport mode access<br>switchport access vlan 2<br>no shutdown<br>exit<br><br>no ip domain-lookup<br>spanning-tree mode pvst<br>spanning-tree vlan 2 priority 8192<br>end<br>wr | enable<br>conf t<br>host switch1<br>int vlan2<br>ip address 192.168.2.30 255.255.255.0<br>no shut<br>end<br><br>conf t<br>vlan 2<br>name General<br>end<br><br>conf t<br>interface range g0/0 - 3<br>switchport mode access<br>switchport access vlan 2<br>no shutdown<br>exit<br><br>no ip domain-lookup<br>spanning-tree mode pvst<br>spanning-tree vlan 2 priority 8192<br>end<br>wr |

These are the resulting configurations showing STP fully functional:
<br>__These configurations can be seen after running the "show spanning-tree vlan 2" command.__
<br>Switch 1 (root bridge): <img width="722" height="426" alt="image" src="https://github.com/user-attachments/assets/665f2806-5efe-4eeb-ab89-01990351bf0a" />

<br> Switch 2: <img width="727" height="452" alt="image" src="https://github.com/user-attachments/assets/279bcf20-7a9c-4997-ac57-3dba335c8309" />

<br> Switch 3: <img width="712" height="439" alt="image" src="https://github.com/user-attachments/assets/91a48be5-6fb2-4663-9d26-f2778d6375e2" />

<br> Switch 4: <img width="714" height="455" alt="image" src="https://github.com/user-attachments/assets/0d61993a-6c54-47c8-9fce-e372903378ab" />

## New topology after stopping “breaking” a link:
<img width="671" height="333" alt="image" src="https://github.com/user-attachments/assets/933a2fb8-78c0-4604-b31d-cbc3e78fd0cd" />

<br>Switch 1 (root bridge): <img width="710" height="457" alt="image" src="https://github.com/user-attachments/assets/1dda3efc-59cc-4536-972c-4c1c0b7b392a" />


<br> Switch 2: <img width="722" height="477" alt="image" src="https://github.com/user-attachments/assets/a46f34ad-a874-4ca0-b77c-b0d3ca17c71c" />


<br> Switch 3: <img width="725" height="484" alt="image" src="https://github.com/user-attachments/assets/016a520b-b900-4d31-a05f-65530ab02bef" />


<br> Switch 4: <img width="724" height="474" alt="image" src="https://github.com/user-attachments/assets/78ba9c0b-0027-496a-b162-59003a59da6c" />
<br>
- “Root” is the root port and is the best path to reaching the root bridge.
- “Desg” means designated port and forwards traffic away from the root port.
- “Altn” just blocks traffic coming in from that port.
- Cost is calculated based on the speed of the cable. The faster the cable, the lower the cost

## Conclusions



