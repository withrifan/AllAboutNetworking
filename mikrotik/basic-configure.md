## Change identity MikroTik

    system identity set name=Router-Office

    system identity print

## Check System Resource

    system resource print

## Add new user & disabled user admin

    user add group=full name=technician password=thisispassword

    user set 0 disabled=yes
    user print

## Config IP Address

ip address add address=<x.x.x.x/x> interface=<interface/ethernet>

    ip address add address=192.168.1.1/24 interface=ether2
