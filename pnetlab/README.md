## Start PNETLab

login with

    username: root
    password: pnet

- type new Root password & repeate
- DNS domain name biarkan default
- Use DHCP IP address
- skip NTP server
- direct connection for Proxy Server configuration
- PNETLab restart and login with user: root & new password

## Install ishare2 in PNETLAB

https://github.com/pnetlabrepo/ishare2

run in PNETLab

    wget -O /usr/sbin/ishare2 https://raw.githubusercontent.com/pnetlabrepo/ishare2/main/ishare2 > /dev/null 2>&1 && chmod +x /usr/sbin/ishare2 && ishare2

## Example command ishare2

show all command

    ishare2

check connection

    ishare2 test

---

search all images

    ishare2 search all

search images by type

    ishare2 search qemu
    ishare2 search bin
    ishare2 search dynamips

search images mikrotik

    ishare2 search mikrotik

search images cisco

    ishare2 search iol

search images kali

    ishare2 search kali

---

pull images mikrotik-6.49.6

    ishare2 pull qemu 613

pull images cisco (i86bi_Linux-L3-AdvEnterpriseK9-M2_157_3_May_2018.bin)

    ishare2 pull bin 14

---

check installed image

    ishare2 installed all
    ishare2 installed bin
    ishare2 installed qemu
    ishare2 installed dynamips
    ishare2 installed docker

> every time you finish downloading images you have to "fix permissions": go to PNETLab > System menu > System Settings > Fix Permissions
