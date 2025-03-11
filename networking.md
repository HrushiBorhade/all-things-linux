# Linux Networking Commands

| Command | Description |
|---------|-------------|
| [`curl`](#curl) | Transfer data from or to a server using various protocols |
| [`wget`](#wget) | Download files from the web, supports HTTP, HTTPS, and FTP |
| [`ping`](#ping) | Test network connectivity to a host by sending ICMP packets |
| [`netstat`](#netstat) | Display network connections, routing tables, and interface statistics |
| [`ifconfig`](#ifconfig) | Configure and display network interface parameters |
| [`traceroute`](#traceroute) | Display the route packets take to reach a network host |
| [`tracepath`](#tracepath) | Similar to traceroute but doesn't require root privileges |
| [`mtr`](#mtr) | Combine ping and traceroute functionality in a real-time interface |
| [`nslookup`](#nslookup) | Query DNS servers for domain name or IP address mapping |
| [`telnet`](#telnet) | Connect to remote systems using the TELNET protocol |
| [`hostname`](#hostname) | Show or set the system's host name |
| [`ip`](#ip) | Show/manipulate routing, devices, policy routing and tunnels |
| [`iwconfig`](#iwconfig) | Configure wireless network interfaces |
| [`ss`](#ss) | Display socket statistics, replacement for netstat |
| [`arp`](#arp) | View or modify the system's ARP cache |
| [`dig`](#dig) | DNS lookup utility, test DNS name servers |
| [`whois`](#whois) | Query WHOIS information for domains |
| [`ifplugstatus`](#ifplugstatus) | Check if network cables are plugged in |
| [`route`](#route) | Show/manipulate IP routing table |
| [`nmap`](#nmap) | Network exploration tool and security scanner |
| [`tcpdump`](#tcpdump) | Capture and analyze network traffic |
| [`nc`](#nc) | Netcat - Swiss army knife for TCP/IP |
| [`ssh`](#ssh) | Secure Shell for remote system access |
| [`scp`](#scp) | Securely copy files between hosts |
| [`rsync`](#rsync) | Fast, versatile file copying and synchronization |
| [`iptables`](#iptables) | Configure IP packet filter rules |
| [`netcat`](#netcat) | Read and write data across network connections |
| [`host`](#host) | DNS lookup utility |

## Command Details

### curl

The `curl` command is a versatile tool for transferring data using various protocols. Here are some common use cases:

1. **Basic GET request:**
```zsh
➜  ~ curl https://jsonplaceholder.typicode.com/todos/1
{
  "userId": 1,
  "id": 1,
  "title": "delectus aut autem",
  "completed": false
}
```

2. **Download file and save with specific name:**
```zsh
➜  ~ curl -o output.pdf https://file-examples.com/wp-content/storage/2017/10/file-sample_150kB.pdf
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1223    0  1223    0     0   2244      0 --:--:-- --:--:-- --:--:--  2244
➜  ~ ls
Desktop                Downloads              Music                  Public                 output.pdf
Developer              Library                Pictures               Screen Studio Projects tasks
Documents              Movies                 Postman                demo-instance.pem
```

3. **POST request with data:**
```zsh
~ curl -X POST -d "name=hrushi&age=22" https://api.restful-api.dev/objects
{
    "status": "created",
    "id": "123"
}
```

4. **Include HTTP headers:**
```zsh
~ curl -H "Authorization: Bearer token 123" https://api.example.com/secure
{
    "secure_data": "protected content"
}
```

5. **Show response headers:**
```zsh
~ curl -I https://www.example.com
HTTP/1.1 200 OK
Content-Type: text/html; charset=UTF-8
Server: ECS (dcb/7F5B)
Last-Modified: Thu, 17 Oct 2019 07:18:26 GMT
ETag: "3147526947"
Accept-Ranges: bytes
```

### wget

The `wget` command is used for downloading files from the web. Here are common use cases:

1. **Basic file download:**
```zsh
~ wget https://example.com/file.zip
--2024-03-20 10:00:01--  https://example.com/file.zip
Resolving example.com... 93.184.216.34
Connecting to example.com|93.184.216.34|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1234567 (1.2M) [application/zip]
Saving to: 'file.zip'

file.zip            100%[===================>]   1.2M  1.1MB/s    in 1.1s

2024-03-20 10:00:03 (1.1 MB/s) - 'file.zip' saved [1234567/1234567]
```

2. **Download with different filename:**
```zsh
~ wget -O custom_name.zip https://example.com/file.zip
```

3. **Download in background:**
```zsh
~ wget -b https://example.com/large_file.zip
Continuing in background, pid 1234.
Output will be written to 'wget-log'.
```

4. **Resume interrupted download:**
```zsh
~ wget -c https://example.com/large_file.zip
```

5. **Download with authentication:**
```zsh
~ wget --user=username --password=password https://example.com/secure/file.zip
```

### ssh

The `ssh` command provides secure remote access. Here are common use cases:

1. **Basic remote login:**
```zsh
~ ssh -i "demo-instance.pem" ubuntu@13.243.108.223
```

### ping

The `ping` command is used to test network connectivity. Here are common use cases:

1. **Basic ping:**
```zsh
~ ping google.com
PING google.com (142.250.190.78): 56 data bytes
64 bytes from 142.250.190.78: icmp_seq=0 ttl=116 time=12.991 ms
64 bytes from 142.250.190.78: icmp_seq=1 ttl=116 time=13.932 ms
64 bytes from 142.250.190.78: icmp_seq=2 ttl=116 time=15.189 ms
```

2. **Specific number of pings:**
```zsh
~ ping -c 3 google.com
PING google.com (142.250.190.78): 56 data bytes
64 bytes from 142.250.190.78: icmp_seq=0 ttl=116 time=12.991 ms
64 bytes from 142.250.190.78: icmp_seq=1 ttl=116 time=13.932 ms
64 bytes from 142.250.190.78: icmp_seq=2 ttl=116 time=15.189 ms

--- google.com ping statistics ---
3 packets transmitted, 3 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 12.991/14.037/15.189/0.901 ms
```

3. **Change ping interval:**
```zsh
~ ping -i 2 google.com
PING google.com (142.250.190.78): 56 data bytes
64 bytes from 142.250.190.78: icmp_seq=0 ttl=116 time=12.991 ms
...2 seconds...
64 bytes from 142.250.190.78: icmp_seq=1 ttl=116 time=13.932 ms
```

4. **Ping with larger packet size:**
```zsh
~ ping -s 1000 google.com
PING google.com (142.250.190.78): 1000 data bytes
1008 bytes from 142.250.190.78: icmp_seq=0 ttl=116 time=14.991 ms
```

### netstat

The `netstat` command displays various network-related information. Here are common use cases:

1. **List all ports (both listening and non-listening):**
```zsh
~ netstat -a
Active Internet connections (including servers)
Proto Recv-Q Send-Q  Local Address          Foreign Address        (state)
tcp4       0      0  localhost.49157        *.*                    LISTEN
tcp4       0      0  *.80                   *.*                    LISTEN
```

2. **Show only listening ports:**
```zsh
~ netstat -l
Active Internet connections (only servers)
Proto Recv-Q Send-Q  Local Address          Foreign Address        (state)
tcp4       0      0  *.80                   *.*                    LISTEN
tcp6       0      0  *.80                   *.*                    LISTEN
```

3. **Display statistics for all protocols:**
```zsh
~ netstat -s
tcp:
    726934 packets sent
        541423 data packets (325557727 bytes)
        924 data packets (565595 bytes) retransmitted
udp:
    15704 packets received
    0 packets to unknown port received
```

4. **Show network interfaces:**
```zsh
~ netstat -i
Name  Mtu   Network       Address            Ipkts Ierrs    Opkts Oerrs  Coll
lo0   16384 <Link>                          1129849     0  1129849     0     0
en0   1500  <Link>                          1871322     0   997076     0     0
```

### ifconfig

The `ifconfig` command is used to configure and display network interface information. Here are common use cases:

1. **Display all interfaces:**
```zsh
~ ifconfig
en0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether a4:83:e7:1e:34:12
	inet6 fe80::1c72:8c45:89ab:cdef%en0 prefixlen 64 secured scopeid 0x6 
	inet 192.168.1.105 netmask 0xffffff00 broadcast 192.168.1.255
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect
	status: active

lo0: flags=8049<UP,LOOPBACK,RUNNING,MULTICAST> mtu 16384
	options=1203<RXCSUM,TXCSUM,TXSTATUS,SW_TIMESTAMP>
	inet 127.0.0.1 netmask 0xff000000 
	inet6 ::1 prefixlen 128 
	inet6 fe80::1%lo0 prefixlen 64 scopeid 0x1 
```

2. **Display specific interface:**
```zsh
~ ifconfig en0
en0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether a4:83:e7:1e:34:12
	inet6 fe80::1c72:8c45:89ab:cdef%en0 prefixlen 64 secured scopeid 0x6 
	inet 192.168.1.105 netmask 0xffffff00 broadcast 192.168.1.255
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect
	status: active
```

3. **Set IP address for interface:**
```zsh
~ sudo ifconfig en0 192.168.1.200
```

4. **Enable/Disable interface:**
```zsh
~ sudo ifconfig en0 down
~ sudo ifconfig en0 up
```

### traceroute

The `traceroute` command shows the route packets take to a network host. Here are common use cases:

1. **Basic traceroute:**
```zsh
~ traceroute google.com
traceroute to google.com (142.250.190.78), 64 hops max, 52 byte packets
 1  router.local (192.168.1.1)  3.052 ms  2.392 ms  2.167 ms
 2  192.168.0.1 (192.168.0.1)  12.120 ms  11.323 ms  10.821 ms
 3  isp-gateway.net (72.14.215.85)  13.123 ms  12.345 ms  13.456 ms
 4  * * *
 5  google-router.net (142.250.190.78)  14.321 ms  13.111 ms  14.234 ms
```

2. **Specify maximum hops:**
```zsh
~ traceroute -m 5 google.com
```

3. **Use ICMP instead of UDP:**
```zsh
~ traceroute -I google.com
```

4. **Show IP addresses only (no DNS):**
```zsh
~ traceroute -n google.com
```

### mtr

The `mtr` command combines ping and traceroute functionality. Here are common use cases:

1. **Basic MTR report:**
```zsh
~ mtr google.com
                                      My traceroute  [v0.95]
hrushis-macbook.local (192.168.1.105) -> google.com (142.250.190.78)
Keys:  Help   Display mode   Restart statistics   Order of fields   quit
                                   Packets               Pings
 Host                            Loss%   Snt   Last   Avg  Best  Wrst StDev
 1. router.local                  0.0%    10    2.1   2.3   2.0   2.9   0.3
 2. isp-gateway.net              0.0%    10   12.1  12.3  11.8  13.1   0.4
 3. google-router.net            0.0%    10   13.2  13.4  13.1  14.2   0.3
```

2. **Report with no DNS resolution:**
```zsh
~ mtr -n google.com
```

3. **Generate report after 10 pings:**
```zsh
~ mtr -r -c 10 google.com
```

### nslookup

The `nslookup` command is used for querying DNS records. Here are common use cases:

1. **Basic DNS lookup:**
```zsh
~ nslookup google.com
Server:		8.8.8.8
Address:	8.8.8.8#53

Non-authoritative answer:
Name:	google.com
Address: 142.250.190.78
```

2. **Query specific record type (MX):**
```zsh
~ nslookup -type=mx google.com
Server:		8.8.8.8
Address:	8.8.8.8#53

Non-authoritative answer:
google.com	mail exchanger = 10 aspmx.l.google.com
google.com	mail exchanger = 20 alt1.aspmx.l.google.com
google.com	mail exchanger = 30 alt2.aspmx.l.google.com
```

3. **Query using specific DNS server:**
```zsh
~ nslookup google.com 1.1.1.1
Server:		1.1.1.1
Address:	1.1.1.1#53

Non-authoritative answer:
Name:	google.com
Address: 142.250.190.78
```

### telnet

The `telnet` command is used for interactive communication with another host. Here are common use cases:

1. **Basic connection test:**
```zsh
~ telnet google.com 80
Trying 142.250.190.78...
Connected to google.com.
Escape character is '^]'.
```

2. **Test specific port:**
```zsh
~ telnet smtp.gmail.com 587
Trying 74.125.133.109...
Connected to smtp.gmail.com.
Escape character is '^]'.
220 smtp.gmail.com ESMTP ready
```

3. **Quick web server test:**
```zsh
~ telnet example.com 80
Trying 93.184.216.34...
Connected to example.com.
Escape character is '^]'.
GET / HTTP/1.1
Host: example.com

HTTP/1.1 200 OK
Content-Type: text/html
```

### hostname

The `hostname` command displays or sets system's host name. Here are common use cases:

1. **Display hostname:**
```zsh
~ hostname
hrushis-macbook.local
```

2. **Display FQDN (Fully Qualified Domain Name):**
```zsh
~ hostname -f
hrushis-macbook.local
```

3. **Display IP address:**
```zsh
~ hostname -i
192.168.1.105
```

4. **Set system hostname (requires sudo):**
```zsh
~ sudo hostname new-macbook-name
```

### ip

The `ip` command is a powerful tool for network configuration. Here are common use cases:

1. **Show all interfaces:**
```zsh
~ ip addr show
1: lo0: <LOOPBACK,MULTICAST,UP,LOWER_UP> mtu 16384
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo0
2: en0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500
    link/ether a4:83:e7:1e:34:12 brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.105/24 brd 192.168.1.255 scope global dynamic en0
```

2. **Show routing table:**
```zsh
~ ip route show
default via 192.168.1.1 dev en0
192.168.1.0/24 dev en0 scope link
```

3. **Add/Delete IP address:**
```zsh
~ sudo ip addr add 192.168.1.200/24 dev en0
~ sudo ip addr del 192.168.1.200/24 dev en0
```

4. **Show network statistics:**
```zsh
~ ip -s link
1: lo0: <LOOPBACK,UP,LOWER_UP> mtu 16384
    RX: bytes  packets  errors  dropped
    234567     1234     0       0
    TX: bytes  packets  errors  dropped
    234567     1234     0       0
```

### iwconfig

The `iwconfig` command is used for wireless network interface configuration. Here are common use cases:

1. **Show wireless interfaces:**
```zsh
~ iwconfig
en0       IEEE 802.11  ESSID:"MyWiFi"  
          Mode:Managed  Frequency:2.462 GHz  Access Point: A1:B2:C3:D4:E5:F6   
          Bit Rate=144.4 Mb/s   Tx-Power=15 dBm   
          Retry min limit:7   RTS thr:off   Fragment thr:off
          Power Management:on
          Link Quality=70/70  Signal level=-43 dBm  
          Rx invalid nwid:0  Rx invalid crypt:0  Rx invalid frag:0
          Tx excessive retries:0  Invalid misc:0   Missed beacon:0
```

2. **Set wireless channel:**
```zsh
~ sudo iwconfig en0 channel 6
```

3. **Set transmission power:**
```zsh
~ sudo iwconfig en0 txpower 15
```

4. **Set wireless mode:**
```zsh
~ sudo iwconfig en0 mode Managed
```

### ss

The `ss` command is a modern replacement for netstat. Here are common use cases:

1. **Show all connections:**
```zsh
~ ss -a
Netid  State      Recv-Q Send-Q    Local Address:Port     Peer Address:Port  
tcp    LISTEN     0      128       127.0.0.1:ipp         *:*
tcp    ESTAB      0      0         192.168.1.105:49153   52.37.85.115:https
```

2. **Show only TCP connections:**
```zsh
~ ss -t
State      Recv-Q Send-Q    Local Address:Port     Peer Address:Port
ESTAB      0      0         192.168.1.105:49153   52.37.85.115:https
```

3. **Show listening sockets:**
```zsh
~ ss -l
Netid  State      Recv-Q Send-Q    Local Address:Port     Peer Address:Port
tcp    LISTEN     0      128       127.0.0.1:ipp         *:*
```

4. **Show process using the socket:**
```zsh
~ ss -p
Netid  State      Recv-Q Send-Q    Local Address:Port     Peer Address:Port   Process
tcp    LISTEN     0      128       127.0.0.1:ipp         *:*                 users:(("cupsd",pid=1234))
```

### arp

The `arp` command is used to display and modify the ARP cache. Here are common use cases:

1. **Display ARP cache:**
```zsh
~ arp -a
? (192.168.1.1) at a4:b1:e9:c2:3d:67 on en0 ifscope [ethernet]
? (192.168.1.105) at a4:83:e7:1e:34:12 on en0 ifscope permanent [ethernet]
```

2. **Display specific entry:**
```zsh
~ arp 192.168.1.1
? (192.168.1.1) at a4:b1:e9:c2:3d:67 on en0 ifscope [ethernet]
```

3. **Delete entry from ARP cache:**
```zsh
~ sudo arp -d 192.168.1.1
```

4. **Add static ARP entry:**
```zsh
~ sudo arp -s 192.168.1.100 00:11:22:33:44:55
```

### dig

The `dig` command is a powerful DNS lookup utility. Here are common use cases:

1. **Basic DNS lookup:**
```zsh
~ dig google.com
;; ANSWER SECTION:
google.com.		299	IN	A	142.250.190.78
```

2. **Query specific record type:**
```zsh
~ dig google.com MX
;; ANSWER SECTION:
google.com.		299	IN	MX	10 aspmx.l.google.com.
google.com.		299	IN	MX	20 alt1.aspmx.l.google.com.
```

3. **Query specific DNS server:**
```zsh
~ dig @8.8.8.8 google.com
;; ANSWER SECTION:
google.com.		299	IN	A	142.250.190.78
```

4. **Reverse DNS lookup:**
```zsh
~ dig -x 142.250.190.78
;; ANSWER SECTION:
78.190.250.142.in-addr.arpa. 86400 IN	PTR	sfo03s29-in-f14.1e100.net.
```

5. **Show trace path:**
```zsh
~ dig +trace google.com
;; Received 13 bytes from 8.8.8.8#53(8.8.8.8) in 88 ms
google.com.		300	IN	A	142.250.190.78
```

### whois

The `whois` command queries domain registration information. Here are common use cases:

1. **Basic domain lookup:**
```zsh
~ whois google.com
Domain Name: GOOGLE.COM
Registry Domain ID: 2138514_DOMAIN_COM-VRSN
Registrar WHOIS Server: whois.markmonitor.com
Registrar URL: http://www.markmonitor.com
Updated Date: 2019-09-09T15:39:04Z
Creation Date: 1997-09-15T04:00:00Z
Registry Expiry Date: 2028-09-14T04:00:00Z
Registrar: MarkMonitor Inc.
```

2. **Query specific WHOIS server:**
```zsh
~ whois -h whois.verisign-grs.com google.com
```

3. **Brief output:**
```zsh
~ whois -b google.com
Domain Name: google.com
Registrar: MarkMonitor Inc.
Creation Date: 1997-09-15
```

4. **IP address lookup:**
```zsh
~ whois 142.250.190.78
NetRange: 142.250.0.0 - 142.251.255.255
CIDR: 142.250.0.0/15
NetName: GOOGLE
NetType: Direct Assignment
Organization: Google LLC (GOGL)
```

### route

The `route` command manages the IP routing table. Here are common use cases:

1. **Display routing table:**
```zsh
~ netstat -nr
Routing tables

Internet:
Destination        Gateway            Flags        Refs      Use   Netif Expire
default            192.168.1.1        UGSc           48        0     en0
127.0.0.1          127.0.0.1         UH              4     5565     lo0
192.168.1.0/24     link#6            UCS             5        0     en0
```

2. **Add static route:**
```zsh
~ sudo route add -net 192.168.2.0/24 192.168.1.1
add net 192.168.2.0: gateway 192.168.1.1
```

3. **Delete route:**
```zsh
~ sudo route delete -net 192.168.2.0/24
delete net 192.168.2.0
```

4. **Add default gateway:**
```zsh
~ sudo route add default 192.168.1.1
add default: gateway 192.168.1.1
```

### nmap

The `nmap` command is a powerful network scanner and security tool. Here are common use cases:

1. **Basic scan of a host:**
```zsh
~ nmap 192.168.1.1
Starting Nmap 7.94 ( https://nmap.org )
Nmap scan report for router.local (192.168.1.1)
Host is up (0.0040s latency).
Not shown: 995 closed tcp ports (conn-refused)
PORT     STATE SERVICE
22/tcp   open  ssh
53/tcp   open  domain
80/tcp   open  http
443/tcp  open  https
8080/tcp open  http-proxy
```

2. **Scan specific ports:**
```zsh
~ nmap -p 80,443 192.168.1.1
Starting Nmap 7.94
PORT    STATE SERVICE
80/tcp  open  http
443/tcp open  https
```

3. **Network sweep (ping scan):**
```zsh
~ nmap -sn 192.168.1.0/24
Starting Nmap 7.94
Nmap scan report for 192.168.1.1
Host is up (0.0040s latency).
Nmap scan report for 192.168.1.105
Host is up (0.000040s latency).
Nmap done: 256 IP addresses (2 hosts up)
```

4. **Service version detection:**
```zsh
~ nmap -sV 192.168.1.1
Starting Nmap 7.94
PORT     STATE SERVICE  VERSION
80/tcp   open  http    nginx 1.18.0
443/tcp  open  https   OpenSSL/1.1.1f
```

5. **OS detection (requires sudo):**
```zsh
~ sudo nmap -O 192.168.1.1
Starting Nmap 7.94
PORT     STATE SERVICE
80/tcp   open  http
Device type: general purpose
Running: Linux 4.X|5.X
OS details: Linux 4.15 - 5.6
```

### tcpdump

The `tcpdump` command captures and analyzes network traffic in real-time. Here are common use cases:

1. **Capture packets on an interface:**
```zsh
~ sudo tcpdump -i en0
tcpdump: verbose output suppressed, use -v or -vv for full protocol decode
listening on en0, link-type EN10MB (Ethernet), capture size 262144 bytes
13:24:30.904943 IP 192.168.1.105.59723 > 172.217.167.46.https: Flags [.], ack 1, win 2048
13:24:30.905794 IP 172.217.167.46.https > 192.168.1.105.59723: Flags [.], ack 77, win 296
```

2. **Capture specific port traffic:**
```zsh
~ sudo tcpdump port 80
tcpdump: verbose output suppressed, use -v or -vv for full protocol decode
listening on en0, link-type EN10MB (Ethernet), capture size 262144 bytes
13:24:35.904943 IP 192.168.1.105.59723 > 93.184.216.34.80: Flags [S]
```

3. **Save capture to file:**
```zsh
~ sudo tcpdump -w capture.pcap
```

### nc (netcat)

The `nc` (netcat) command is a versatile networking utility. Here are common use cases:

1. **Test port connectivity:**
```zsh
~ nc -zv google.com 443
Connection to google.com port 443 [tcp/https] succeeded!
```

2. **Create simple chat server:**
```zsh
~ nc -l 1234                  # Server
~ nc localhost 1234           # Client
```

3. **Transfer file:**
```zsh
~ nc -l 1234 > received_file  # Server
~ nc localhost 1234 < file    # Client
```



### scp

The `scp` command securely copies files between hosts. Here are common use cases:

1. **Copy file to remote host:**
```zsh
~ scp file.txt user@remote-host:/path/to/destination
```

2. **Copy directory recursively:**
```zsh
~ scp -r directory/ user@remote-host:/path/to/destination
```

3. **Copy from remote to local:**
```zsh
~ scp user@remote-host:/path/to/file.txt local-file.txt
```

### rsync

The `rsync` command efficiently transfers and synchronizes files. Here are common use cases:

1. **Basic file sync:**
```zsh
~ rsync -av source/ destination/
sending incremental file list
file1.txt
file2.txt
```

2. **Remote sync:**
```zsh
~ rsync -av source/ user@remote-host:/path/to/destination/
```

3. **Dry run (show what would be transferred):**
```zsh
~ rsync -av --dry-run source/ destination/
```

### iptables

The `iptables` command configures IP packet filtering rules. Here are common use cases:

1. **List all rules:**
```zsh
~ sudo iptables -L
Chain INPUT (policy ACCEPT)
target     prot opt source               destination

Chain FORWARD (policy ACCEPT)
target     prot opt source               destination

Chain OUTPUT (policy ACCEPT)
target     prot opt source               destination
```

2. **Add rule to allow incoming SSH:**
```zsh
~ sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

3. **Block IP address:**
```zsh
~ sudo iptables -A INPUT -s 192.168.1.100 -j DROP
```

### netcat

The `netcat` command is a versatile networking utility. Here are common use cases:

1. **Read and write data across network connections:**
```zsh
~ nc -l 1234                  # Server
~ nc localhost 1234           # Client
```

2. **Transfer file:**
```zsh
~ nc -l 1234 > received_file  # Server
~ nc localhost 1234 < file    # Client
```

### host

The `host` command is a simple DNS lookup utility. Here are common use cases:

1. **Basic DNS lookup:**
```zsh
~ host google.com
google.com has address 142.250.190.78
google.com has IPv6 address 2607:f8b0:4004:c09::6a
```

2. **Reverse DNS lookup:**
```zsh
~ host 142.250.190.78
78.190.250.142.in-addr.arpa domain name pointer sfo03s29-in-f14.1e100.net.
```

3. **Query MX records:**
```zsh
~ host -t MX google.com
google.com mail is handled by 10 aspmx.l.google.com.
google.com mail is handled by 20 alt1.aspmx.l.google.com.
```

