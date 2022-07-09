# DHCP-SNOOPING-CONFIGURATION
----------------------------
DHCP-SERVER
------------
int g0/0
ip address 192.168.1.1 255.255.255.0
no shutdown 
exit
ip dhcp pool lan
default-router 192.168.1.1
network 192.168.1.0 255.255.255.0
end

DHCP-POOL SNOOPING
------------------
SW-1
-----
SW1(config)#ip dhcp snooping vlan 1
#int fa0/6
ip dhcp snooping trust
exit
SW1(config)#no ip dhcp snooping information option 
End 	

Fake DHCP-POOL
-------------
int g0/0
ip address 10.0.0.1 255.0.0.0
no shutdown 
exit
ip dhcp pool abc
default-router 10.0.0.1
network 10.0.0.0 255.0.0.0
![DHCP-SNOOPING ](https://user-images.githubusercontent.com/106605770/178120594-91ab2c9a-b0af-4102-b444-cb07a2b3f996.jpg)
