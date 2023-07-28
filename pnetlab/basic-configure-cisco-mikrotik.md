## Interface Connection

- Mikrotik :
  - eth1 : 192.168.1.1/30
  - eth2 : 192.168.2.1/24
- Cisco Router :
  - e0/0 : 192.168.1.2/30
  - e0/1 : 192.168.3.1/24
  - e0/2.10 : 192.168.10.1/24
  - e0/2.20 : 192.168.20.1/24
- Cisco switch :
  - e0/0 : trunk
  - e0/1 : access (192.168.10.0/24)
  - e0/2 : access (192.168.20.0/24)
- VPC1 : 192.168.2.2/24
- VPC2 : 192.168.3.2/24
- VPC3 : 192.168.10.2/24
- VPC4 : 192.168.20.2/24

---

## MikroTik

configure IP address

    ip add add add=192.168.1.1/30 interface=ether1
    ip add add add=192.168.2.1/24 interface=ether2

add static route

    ip route add dst-address=192.168.3.0/24 gateway=192.168.1.2
    ip route add dst-address=192.168.10.0/24 gateway=192.168.1.2
    ip route add dst-address=192.168.20.0/24 gateway=192.168.1.2

---

## Cisco Router

configure IP address

    int e0/0
    ip add 192.168.1.2 255.255.255.252
    no sh
    int e0/1
    ip add 192.168.3.1 255.255.255.0
    no sh
    exit

add static route

    ip route 192.168.2.0 255.255.255.0 192.168.1.1

config encapsulation dot1q

    int e0/2
    no sh

    int e0/2.10
    encapsulation dot1q 10
    ip add 192.168.10.1 255.255.255.0
    exit

    int e0/2.20
    encapsulation dot1q 20
    ip add 192.168.20.1 255.255.255.0
    exit

---

## Cisco Switch

add vlan 10 & vlan 20

    vlan 10
    name office1
    vlan20
    name office2
    exit

setting switchport mode access

    int e0/1
    switchport mode access
    switchport access vlan 10
    exit

    int e0/2
    switchport mode access
    switchport access vlan 20
    exit

config switchport mode trunk

    int e0/0
    switchport trunk encapsulation dot1q
    switchport mode trunk

---

## VPC1

setting IP

    ip 192.168.2.2/24 192.168.2.1

## VPC2

setting IP

    ip 192.168.3.2/24 192.168.3.1

## VPC3

setting IP

    ip 192.168.10.2/24 192.168.10.1

## VPC4

setting IP

    ip 192.168.20.2/24 192.168.20.1
