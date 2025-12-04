# EXTENDED-ACL
EXTENDED ACCESS CONTROL LIST
An extended ACL was configured between two LAN areas: the client-side LAN (192.168.0.0/24) and the server-side LAN (192.168.1.0/24), interconnected via the 192.168.2.0/24 network. The ACL was applied to allow only HR department devices from the client-side to send ICMP requests to server-side devices and to permit access to the server’s web services, while blocking ICMP and other traffic from all other client-side devices.


# EXTENDED ACL CLI-COMMANDS

Router# config terminal

Router(config)# ip access-list extended 102

Router(cofig - ext - nacl)# permit TCP 192.168.0.0 0.0.0.255 host 192.168.1.4 eq 80

Exit

Router(config)# int gig 0/0/0

Router(config - if)# ip access-group 102 in

EXIT

Router# config terminal

Router(config)# ip access-list extended 102

Router(cofig - ext - nacl)# permit ICMP 192.168.0.2 255.255.255.0 192.168.1.0 255.255.255.0

Router(cofig - ext - nacl)# access-list 102 deny ICMP any any

Exit

Router(config)# int gig 0/0/0

Router(config - if)# ip access-group 102 in
