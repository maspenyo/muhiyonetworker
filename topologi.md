# Topologi Jaringan Server

![Logo](image/topologi.png)

# Alokasi Jaringan
- [internet] to [router] : dynamic
- [router] to [client] : 192.168.10.0/24
- [router] to [main server] : 172.17.15.0/24
- [main server] to [data server] : 10.11.12.2/30
- [main server] to [app server] : 10.11.12.7/29

# Detail IP Address
## [ router ]
- ether1 : dhcp_client
- ether2 : 172.16.10.1/30
- ether3 : 192.168.10.1/24

## [ client ]
- eth0 : dhcp_client_from_router

## [ main server ]
- eth0 : 172.17.15.254/30
- eth1 : 172.16.10.5/30
- eth2 : 172.16.10.9/29

## [ data server ]
- eth0 : 172.16.10.6/30

## [ app server 1 ]
- eth0 : 172.16.10.10/29

## [ app server 1 ]
- eth0 : 172.16.10.11/29

# Detail Service
## [ router ]
- dhcp server
- nat
- firewall
- pptp

## [ main server ]
- ssh server
- dns server
- load balancing
- firewall
- ntp server

## [ data server ]
- nfs server
- database server (postgresql & mariadb)
- samba server

## [ app server 1 ]
- nginx
- nfs-client
- lms, wordpress

## [ app server 2 ]
- apache2
- nfs-client
- lms, wordpress
