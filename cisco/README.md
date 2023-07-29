# Basic Config Cisco

## Router

### Config IP Address

    int f0/0
    ip add 192.168.1.1 255.255.255.0
    no sh

### Add Static Route

    ip route 192.168.2.0 255.255.255.0 192.168.1.1

### Config encapsulation dot1q

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

## Switch

### Add vlan 10 & vlan 20

    vlan 10
    name office1
    vlan20
    name office2
    exit

### Setting switchport mode access

    int e0/1
    switchport mode access
    switchport access vlan 10
    exit

    int e0/2
    switchport mode access
    switchport access vlan 20
    exit

### Config switchport mode trunk

    int e0/0
    switchport trunk encapsulation dot1q
    switchport mode trunk
