in pc 1:
Router>enable
Router#config terminal
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#line console 0
Router(config-line)#enable secret 1234
Router(config)#end
Router#
%SYS-5-CONFIG_I: Configured from console by console

in pc 2:
Router>enable
Router#config terminal
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#line console 0
Router(config-line)#enable secret 1234
Router(config)#end
Router#exit

in pc 3:

Router>enable
Router#
Router#
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#line console 0
Router(config-line)#enable secret 1234
Router(config)#end
Router#
%SYS-5-CONFIG_I: Configured from console by console
exit













in router 1:
Router>enable
Password: 
Router#config terminal
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#hostname R1
R1(config)#interface gig0/0
R1(config-if)#ip address 192.168.1.1 255.255.255.0
R1(config-if)#no shutdown

R1(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up

R1(config)#interface serial 0/0/1
R1(config-if)#ip address 10.0.0.1 255.0.0.0
R1(config-if)#clock rate 64000
R1(config-if)#no shutdown

%LINK-5-CHANGED: Interface Serial0/0/1, changed state to down
R1(config-if)#exit
R1(config)#interface serial 0/0/0
R1(config-if)#ip address 30.0.0.1 255.0.0.0
R1(config-if)#no shutdown

%LINK-5-CHANGED: Interface Serial0/0/0, changed state to down
R1(config-if)#exit





in router 2:
Router>enable
Password: 
Router#config terminal
Enter configuration commands, one per line.  End with CNTL/Z.	
Router(config)#hostname R2
R2(config)#interface gig0/0
R2(config-if)#ip address 192.168.2.1 255.0.0.0
R2(config-if)#no shutdown

R2(config-if)#ip address 192.168.2.1 255.255.255.0
R2(config-if)#exit
R2(config)#interface serial 
%SYS-5-CONFIG_I: Configured from console by console

%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, chainterface serial 
% Incomplete command.
R2(config)#interface serial 
% Incomplete command.
R2(config)#interface serial 0/0/0
R2(config-if)#ip address 20.0.0.1 255.0.0.0
R2(config-if)#clock rate 6400
Unknown clock rate
R2(config-if)#clock rate 64000
R2(config-if)#no shutdown

%LINK-5-CHANGED: Interface Serial0/0/0, changed state to down
R2(config-if)#exit
R2(config)#interface serial 0/0/1
R2(config-if)#ip address 10.0.0.2 255.0.0.0
R2(config-if)#clock rate 64000
This command applies only to DCE interfaces
R2(config-if)#no shutdown

R2(config-if)#
%LINK-5-CHANGED: Interface Serial0/0/1, changed state to up
exit
R2(config)#
%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/0/1, changed state to up


in router 3:
Router>enable
Password: 
Router#config terminal
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#hostname R3
R3(config)#interface gig0/0
R3(config-if)#ip address 192.168.3.1 255.255.255.0
R3(config-if)#no shutdown

R3(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up

R3(config-if)#exit
R3(config)#interface serial 0/0/0
R3(config-if)#ip address 20.0.0.2 255.0.0.0
R3(config-if)#clock rate 64000
This command applies only to DCE interfaces
R3(config-if)#no shutdown
R3(config-if)#exit
R3(config)#interface serial 0/0/1
R3(config-if)#ip address 30.0.0.2 255.0.0.0
R3(config-if)#clock rate 64000
R3(config-if)#no shutdown

R3(config-if)#
%LINK-5-CHANGED: Interface Serial0/0/1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/0/1, changed state to up




configuring ospf
router 1:
R1>enable
Password: 
R1#config t
Enter configuration commands, one per line.  End with CNTL/Z.
R1(config)#router ospf 1
R1(config-router)#network 192.168.1.0 0.0.0.255 area 0
R1(config-router)#network 10.0.0.0 0.255.255.255 area 0
R1(config-router)#network 30.0.0.0 0.255.255.255 area 0

in router2:

R2>enable
Password: 
R2#config terminal
Enter configuration commands, one per line.  End with CNTL/Z.
R2(config)#router ospf 1
R2(config-router)#network 192.168.2.0 0.0.0.255 area 0
R2(config-router)#network 10.0.0.0 0.255.255.255 area 0
R2(config-router)#network 20.0.0.0 0.255.255.255 area 0