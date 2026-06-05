#Project Overview
This project demonstrates the implementation of VLANs, Inter-VLAN Routing, and OSPF routing using Cisco Packet Tracer.
The network is segmented into multiple VLANs.
Communication between VLANs is enabled through Router-on-a-Stick configuration, while OSPF is used to dynamically exchange routing information between routers.
#Skills practiced:
-Creating and configuring VLANs on Cisco switches.
-Assigning switch ports to specific VLANs.
-Configuring trunk links between switches and routers.
-Implementing Inter-VLAN Routing using Router-on-a-Stick.
-Configuring OSPF routing.
-Establishing OSPF neighbor relationships.
-Verify routing tables and learned routes.
-Troubleshooting VLAN and OSPF connectivity issues.
-Testing end-to-end communication between hosts on different networks.
#Technologies Used
Cisco Packet Tracer
VLANs
IEEE 802.1Q Trunking
Router-on-a-Stick
OSPF Version 2
IPv4 Addressing
Cisco IOS CLI
# Basic configs:
VLAN Creation:
-vlan 10
 name SALES
-vlan 20
 name HR
-vlan 30
 name IT
 
 Trunk Configuration:
-interface g0/1
 switchport mode trunk
 
 Router-on-a-stick:
-interface g0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

-interface g0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0

-interface g0/0.30
 encapsulation dot1Q 30
 ip address 192.168.30.1 255.255.255.0
 
 OSPF Configuration:
 router ospf 1
network 10.0.0.0 0.0.0.255 area 0
network 192.168.10.0 0.0.0.255 area 0
network 192.168.20.0 0.0.0.255 area 0
network 192.168.30.0 0.0.0.255 area 0
network 192.168.40.0 0.0.0.255 area 1
network 192.168.50.0 0.0.0.255 area 1

network 192.168.60.0 0.0.0.255 area 2
network 192.168.70.0 0.0.0.255 area 2

