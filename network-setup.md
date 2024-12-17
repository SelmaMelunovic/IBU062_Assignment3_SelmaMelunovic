1.Router:
Model: Cisco 1941 Router
- GigabitEthernet0/0/0 - connected with first switch
- GigsbitEthernet0/0/1 - connected with second switch

1. Switches:
Model: Cisco 2960-24TT
Connected devices:
-PC0,PC1,Server0,Laptop0,PC3
2. Switch
Model Cisco 2960-24TT
Connected devices:
-PC2, Server1, Server2,PC4

3. Hosts(PCs, Laptop, Switches):
PC0:
IP Address: 168.90.0.2
Connected to Switch 1
PC1: IP Address: 168.90.0.3
Connected to Switch 1
Server0:
IP address: 168.90.0.5
Connected to Switch 1
Laptop0:
IP address: 168.90.0.4
Connected to Switch 1
PC2:
IP address: 210.3.14.4
Connected to Switch 2
Server1:
IP address: 210.3.14.2
Connected to Switch 2
Server2:
IP address: 210.3.14.3
Connected to Switch 2
PC3:
IP address: 168.90.0.6
Connected to Switch 1
PC4:
IP address: 210.3.14.5
Connected to Switch 2


'DHCP commands and steps'
First Switch:
id dhcp pool Network_1
network 168.90.0.0 255.255.0.0
default-router 168.90.0.1
exit
Second Switch:
ip pool Network_2
network 210.3.14.0 255.255.255.0
default-router 210.3.14.1
exit
interface GigabitEthernet0/0
ip address 168.90.0.1 255.255.0.0
no shutdown
interface GigabitEthernet0/1
ip address 210.3.14.1 255.255.255.0
no shutdown

(I thought we needed this from the start)