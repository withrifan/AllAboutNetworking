# Basic Config MikroTik

## RouterOS v6

### Change identity

    system identity set name=Router-Office

    system identity print

### Check System Resource

    system resource print

### Add new user & disabled user admin

    user add group=full name=technician password=thisispassword

    user set 0 disabled=yes
    user print

### Add IP Address

ip address add address=<x.x.x.x/x> interface=<interface/ethernet>

    ip address add address=192.168.1.1/24 interface=ether2

### Config Static Route

ip route add dst-address=<x.x.x.x/x> gateway=<x.x.x.x/x>

    ip route add dst-address=192.168.10.0/24 gateway=10.10.10.2

### Basic Firewall NAT

Configuration so that clients from the MikroTik network can connect to the internet via NAT
