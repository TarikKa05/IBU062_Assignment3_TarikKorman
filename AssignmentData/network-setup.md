Devices found to be connected to my network:
1. 2811 Router 0 IP: 168.90.0.1   
2. 2960-24TT Switch 0 IP: 168.90.0.0
3. Server-PT Server0 IP:169.254.49.9
4. PC-PT PC0 IP:168.90.0.3
5. PC-PT PC1 IP: 168.90.0.2
6. Laptop-PT Laptop0 IP:169.254.110.84
7. 2960-24TT Switch 1 IP: 210.3.14.0
8. PC-PT PC2 IP:169.254.2.133
9. Server-PT Server 2 IP:169.254.114.87
10. Server-PT Server 1 IP:169.254.201.56
11. PC-PT PC4 IP: 210.3.14.2
12. PC-PT PC3 IP: 168.90.0.4

Explanation of DHCP commands and steps:
-I added devices: router, switch, PCs in work space
-I used straight-through cable to connect router to switch and PCs to switch
-I checked if all devices are connected
-Then I opened router, went to CLI tab, and entered privileged mode using command enable 
-I entered global cofiguration mode using command configure terminal
-I created DHCP pool using command ip dhcp pool MYPOOL
-I specified network addresses and subnet masks, example network network 168.90.0.0 255.255.255.0
-I set up router to act as default gateway using command default-router 168.90.0.1
-I exited the DHCP configuration mode using command exit
-I configured router interface using commands
interface FastEthernet0/0 
ip address 168.90.0.1. 255.255.255.0
no shutdown
-I exited interface configuration mode using command exit
-Configured PCs by going to Desktop tab in PC, and opening IP configuration
-I set IP configuration to DHCP by selecting DHCP, and the PC will request IP address frm the DHCP server
-To verify configuration, I checked DHCP bindings on the router with command show ip dhcp binding
-I pinged the router from the server using command ping 168.90.0.4.