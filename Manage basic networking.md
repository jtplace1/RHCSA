Manage basic networking

# Manage basic networking

 - Configure IPv4 and IPv6 addresses
-  
-  Configure network services to start automatically at boot
-  Restrict network access using firewall-cmd/firewall

| **Networking**                                               |                                                         |
|--------------------------------------------------------------|---------------------------------------------------------|
| nmcli                                                        |                                                         |
| nmcli con add type ethernet con-name eth1 inflame enp0s3 ipv4 10.0.2.10/24 gw4 192.168.1.254 | Setting you IP address with the nmcli command                |
| nmcli device wifi connect \<SSID> password \<password>       | Connecting to a wireless network with NMCLI             |
| Nmcli con up \<connection name>                              | Enable a new connection with NMCLI                      |
| nmcli con show                                               | Show if there is a Wifi module active                   |
| nmcli device wifi list                                       | Show all the available networks                         |
| nmcli device status                                          | display network interfaces                              |
| Ip Route                                                     | Show default routes on your local host                  |
| ethtool \<interface>                                         | Display ethernet settings                               |
| iwconfig \<wlan device> essid “wlan name” key s:password     | Setting SSID for wireless interface                     |  | Ip address                                                   | Showing all the ip adresses for the interfaces          |
| /etc/sysconfig/network-scripts                               | Config location for Red Hat systems                     |
| Route add default gw 192.168.0.254                           | Set a default gateway on a host                         |
| Ip neighbour show / arp -a                                   | Show the ARP table                                      |
| /etc/resolv.conf                   | Dns resolver   search localdomain (for fqdn) nameserver 192.168.82.2 (dns server) |
| /etc/nsswitch.conf     | Config file that has been used to get the correct order in witch a dns server needs to search |
|nmcli con reload | reload connection after making changes |

| **Configure hostname resolution** |             |
| -------- | ----------- |
|  getnet host       |                 |
| hostname           |    print hostname             |
| /etc/hostname      |   configure hostname         |
| hostnamectl         |     refresh hostname       |
| /etc/resolve.config      |    configure dns        |
| nmcli con modify <wifi name> ipv4.dns "8.8.8.8" |  |
|systemctl restart NetworkManager| |
| /etc/hosts/       |   configure local dns      |


| **Bonding NIC’s**                         | For load balancing, aggregation or active/pasive    |
| ----------------------------------------- | --------------------------------------------------- |
| modprobe bonding                          | Creating a bon0 interface                           |
| Ip link add bon0 type bond mode <mode nr> | Creating a bond (there are different kind of modes) |
| Sudo ip link set eth1 master bond0        | Adding interface to a bond                          |



| **Troubleshooting**                          |                                                              |
| -------------------------------------------- | ------------------------------------------------------------ |
| Ping 1.1.1.1                                 |                                                              |
| Ping6 fe80::c418:2ed0:aead:cbce%**enp0s3**   | When sending out packages of a link local address you must specify the outgoing interface! |
| Tracepath 1.1.1.1                            | Tracing routes                                               |
| Dig \<domain name>                           | Getting all the DNS adresses                                 |
| Getent hosts                                 | Looking up all the hosts in the /etc/hosts file              |
| ss                                      | Showing all the current open network connections             |
| Ss -anpt                                     | Showing which system process are using which network sockets (currently) |
| lsof -i                                      | Show open network ports                                      | 
| Nc                                           | Netcat utility (reading and writing to or from a network port) |
| Route del default or ip route del default    | Removing the default route (gateway)                         |

| **Networking**             |                                                              |
| -------------------------- | ------------------------------------------------------------ |
| Ip link show               | Show the link stat of all the interfaces                     |
| Ip -s link show            | Show the current link statistics (packets sent, received etc.) |
|                            |                                                              |
| Ss -lt                     | Showing all the listening ports on the current system        |
| Nmcli dev show \<NICname\> | Show status of a interface                                   |

