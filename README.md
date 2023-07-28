This is a special repository for Computer Network Configuration

- [Cisco](cisco)
- [MikroTik](mikrotik)
- [PNETLab](pnetlab)

---

Several commands for testing network connections and troubleshooting

- ipconfig

  Displays information about the IP Address configuration on Windows devices

        ipconfig
        ipconfig ?
        ipconfig /release
        ipconfig /renew
        ipconfig /flushdns
        ipconfig /displaydns

- netstat

  Displays protocol statistics and TCP/IP connections that are currently running on the network on Windows & Linux devices

        netstat
        netstat ?
        netstat -a
        netstat -p TCP

- nslookup

  Displays IP information for a domain

        nslookup rifan.web.id

- netsh

  Administrator tool of windows for network configuration and display running information

        netsh ?
        netsh interface ip show interface
        netsh wlan show profile

- ping
  Test the network connection, whether a host can be reached via the ICMP protocol

        ping 192.168.1.2
        ping rifan.web.id

- tracert / traceroute

  Displays a list of routers that have passed to the destination host

        tracert rifan.web.id
        traceroute rifan.web.id
