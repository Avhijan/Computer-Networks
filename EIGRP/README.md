for router 0
Router>en
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.

Router(config)#interface gig 0/0 
Router(config-if)#ip address 10.0.0.1 255.0.0.0
Router(config-if)#no shut
Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up
Router(config-if)#exit

Router(config)#interface gig0/1
Router(config-if)#ip address 20.0.0.2 255.0.0.0
Router(config-if)#no shut
Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up
Router(config-if)#exit




for router1
Router>en
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#interface gig0/0
Router(config-if)#ip address 20.0.0.1 255.0.0.0
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up

Router(config-if)#interface gig0/1
Router(config-if)#ip address 20.0.0.1 255.0.0.0
Router(config-if)#no shut


Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

Router(config-if)#exit

Router(config)#interface gig0/2
Router(config-if)#ip address 40.0.0.1 255.0.0.0
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/2, changed state to up

Router(config-if)#exit


For router 2
Router>en
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#interface gig 0/0
Router(config-if)#ip address 50.0.0.1 255.0.0.0
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up
exit
Router(config)#interface gig 0/1
Router(config-if)#ip address 40.0.0.2 255.0.0.0
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

Router(config-if)#exit




Routing with EIGRP:
in router 0:
Router>en
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#router eigrp 10
Router(config-router)#network 10.0.0.0
Router(config-router)#network 20.0.0.0


in router 1:
Router>en
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#router eigrp 10
Router(config-router)#network 20.0.0.0
Router(config-router)#network 30.0.0.0
Router(config-router)#network 40.0.0.0


in router 2
Router>en
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#router eigrp 10
Router(config-router)#network 50.0.0.0
Router(config-router)#network 40.0.0.0