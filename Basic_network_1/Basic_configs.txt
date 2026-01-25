## SW1 config
Building configuration...

Current configuration : 2103 bytes
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname SW1
!
enable secret 5 $1$mERr$NJdjwh5wX8Ia/X8aC4RIu.
!
!
!
!
!
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface FastEthernet0/1
 description ## EndPoint ##
!
interface FastEthernet0/2
 description ## EndPoint ##
!
interface FastEthernet0/3
 description ## EndPoint ##
!
interface FastEthernet0/4
 description ## EndPoint ##
!
interface FastEthernet0/5
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/6
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/7
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/8
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/9
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/10
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/11
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/12
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/13
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/14
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/15
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/16
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/17
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/18
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/19
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/20
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/21
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/22
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/23
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/24
 description ## Not in use ##
 shutdown
!
interface GigabitEthernet0/1
 description ## To R1 ##
!
interface GigabitEthernet0/2
 description ## Not in use ##
 shutdown
!
interface Vlan1
 no ip address
 shutdown
!
!
!
!
line con 0
!
line vty 0 4
 login
line vty 5 15
 login
!
!
!
!
end

## SW2 config
Building configuration...

Current configuration : 2103 bytes
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname SW2
!
enable secret 5 $1$mERr$NJdjwh5wX8Ia/X8aC4RIu.
!
!
!
!
!
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface FastEthernet0/1
 description ## EndPoint ##
!
interface FastEthernet0/2
 description ## EndPoint ##
!
interface FastEthernet0/3
 description ## EndPoint ##
!
interface FastEthernet0/4
 description ## EndPoint ##
!
interface FastEthernet0/5
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/6
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/7
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/8
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/9
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/10
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/11
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/12
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/13
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/14
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/15
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/16
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/17
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/18
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/19
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/20
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/21
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/22
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/23
 description ## Not in use ##
 shutdown
!
interface FastEthernet0/24
 description ## Not in use ##
 shutdown
!
interface GigabitEthernet0/1
 description ## To R1 ##
!
interface GigabitEthernet0/2
 description ## Not in use ##
 shutdown
!
interface Vlan1
 no ip address
 shutdown
!
!
!
!
line con 0
!
line vty 0 4
 login
line vty 5 15
 login
!
!
!
!
end

## R1 config
Building configuration...

Current configuration : 790 bytes
!
version 15.4
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname R1
!
!
!
enable secret 5 $1$mERr$NJdjwh5wX8Ia/X8aC4RIu.
!
!
!
!
!
!
ip cef
no ipv6 cef
!
!
!
!
!
!
!
!
!
!
!
!
spanning-tree mode pvst
!
!
!
!
!
!
interface GigabitEthernet0/0/0
 description ## To SW1 ##
 ip address 10.0.0.1 255.0.0.0
 duplex auto
 speed auto
!
interface GigabitEthernet0/0/1
 description ## To SW2 ##
 ip address 192.168.0.1 255.255.255.0
 duplex auto
 speed auto
!
interface GigabitEthernet0/0/2
 description ## Not in use ##
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface Vlan1
 no ip address
 shutdown
!
ip classless
!
ip flow-export version 9
!
!
!
!
!
!
!
line con 0
!
line aux 0
!
line vty 0 4
 login
!
!
!
end
