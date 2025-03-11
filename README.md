<div style="display: flex; flex-direction:column; align-items: start;">
    <img src="linux-mascot.gif" alt="Linux Mascot Falling" style="width: 70%;">
    <pre style="width: 100%; margin: 0; font-family: monospace; line-height: 1.2; font-size: 14px; background: transparent; padding: 0; border: none;">
 █████╗ ██╗     ██╗         ████████╗██╗  ██╗██╗███╗   ██╗ ██████╗ ███████╗        ██╗     ██╗███╗   ██╗██╗   ██╗██╗  ██╗
██╔══██╗██║     ██║         ╚══██╔══╝██║  ██║██║████╗  ██║██╔════╝ ██╔════╝        ██║     ██║████╗  ██║██║   ██║╚██╗██╔╝
███████║██║     ██║            ██║   ███████║██║██╔██╗ ██║██║  ███╗███████╗        ██║     ██║██╔██╗ ██║██║   ██║ ╚███╔╝ 
██╔══██║██║     ██║            ██║   ██╔══██║██║██║╚██╗██║██║   ██║╚════██║        ██║     ██║██║╚██╗██║██║   ██║ ██╔██╗ 
██║  ██║███████╗███████╗       ██║   ██║  ██║██║██║ ╚████║╚██████╔╝███████║        ███████╗██║██║ ╚████║╚██████╔╝██╔╝ ██╗
╚═╝  ╚═╝╚══════╝╚══════╝       ╚═╝   ╚═╝  ╚═╝╚═╝╚═╝  ╚═══╝ ╚════╝ ╚══════╝        ╚══════╝╚═╝╚═╝  ╚═══╝ ╚═════╝ ╚═╝  ╚═╝</pre>
</div>

| Category | Commands |
|----------|----------|
| [**Networking Commands**](networking.md) | [`curl`](networking.md#curl) [`wget`](networking.md#wget) [`ssh`](networking.md#ssh) [`ping`](networking.md#ping) [`netstat`](networking.md#netstat) [`ifconfig`](networking.md#ifconfig) [`traceroute`](networking.md#traceroute) [`tracepath`](networking.md#tracepath) [`mtr`](networking.md#mtr) [`nslookup`](networking.md#nslookup) [`telnet`](networking.md#telnet) [`hostname`](networking.md#hostname) [`ip`](networking.md#ip) [`iwconfig`](networking.md#iwconfig) [`ss`](networking.md#ss) [`arp`](networking.md#arp) [`dig`](networking.md#dig) [`whois`](networking.md#whois) [`ifplugstatus`](networking.md#ifplugstatus) [`route`](networking.md#route) [`nmap`](networking.md#nmap) [`tcpdump`](networking.md#tcpdump) [`nc`](networking.md#nc) [`scp`](networking.md#scp) [`rsync`](networking.md#rsync) [`iptables`](networking.md#iptables) [`netcat`](networking.md#netcat) [`host`](networking.md#host) |
| [**System Level Commands**](system.md) | [`uname`](system.md#uname) [`uptime`](system.md#uptime) [`date`](system.md#date) [`who`](system.md#who) [`whoami`](system.md#whoami) [`which`](system.md#which) [`id`](system.md#id) [`sudo`](system.md#sudo) [`shutdown`](system.md#shutdown) [`reboot`](system.md#reboot) [`apt`](system.md#apt) [`yum`](system.md#yum) [`dnf`](system.md#dnf) [`pacman`](system.md#pacman) [`portage`](system.md#portage) |
| [**User & Group Management**](user-and-group-management.md) | [`sudo`](user-and-group-management.md#sudo) [`useradd`](user-and-group-management.md#useradd) [`whoami`](user-and-group-management.md#whoami) [`su`](user-and-group-management.md#su) [`passwd`](user-and-group-management.md#passwd) [`userdel`](user-and-group-management.md#userdel) [`groupadd`](user-and-group-management.md#groupadd) [`gpasswd`](user-and-group-management.md#gpasswd) [`groupdel`](user-and-group-management.md#groupdel) |
| [**File Permissions**](file-permissions.md) | [`ls`](file-permissions.md#ls) [`chmod`](file-permissions.md#chmod) [`chown`](file-permissions.md#chown) [`chgrp`](file-permissions.md#chgrp) [`umask`](file-permissions.md#umask) |
| [**Compression Commands**](compression.md) | [`zip`](compression.md#zip) [`gzip`](compression.md#gzip) [`gunzip`](compression.md#gunzip) [`tar`](compression.md#tar) [`untar`](compression.md#untar) |
| [**Pro Linux Commands**](pro-linux-commands.md) | [`awk`](pro-linux-commands.md#awk) [`sed`](pro-linux-commands.md#sed) [`grep`](pro-linux-commands.md#grep) |

# Linux Commands

### Networking Commands
[View detailed networking commands guide](networking.md)

| Command | Description |
|---------|-------------|
| [`curl`](networking.md#curl) | Transfer data from or to a server using various protocols |
| [`wget`](networking.md#wget) | Download files from the web, supports HTTP, HTTPS, and FTP |
| [`ssh`](networking.md#ssh) | Secure Shell for remote system access |
| [`ping`](networking.md#ping) | Test network connectivity to a host by sending ICMP packets |
| [`netstat`](networking.md#netstat) | Display network connections, routing tables, and interface statistics |
| [`ifconfig`](networking.md#ifconfig) | Configure and display network interface parameters |
| [`traceroute`](networking.md#traceroute) | Display the route packets take to reach a network host |
| [`tracepath`](networking.md#tracepath) | Similar to traceroute but doesn't require root privileges |
| [`mtr`](networking.md#mtr) | Combine ping and traceroute functionality in a real-time interface |
| [`nslookup`](networking.md#nslookup) | Query DNS servers for domain name or IP address mapping |
| [`telnet`](networking.md#telnet) | Connect to remote systems using the TELNET protocol |
| [`hostname`](networking.md#hostname) | Show or set the system's host name |
| [`ip`](networking.md#ip) | Show/manipulate routing, devices, policy routing and tunnels |
| [`iwconfig`](networking.md#iwconfig) | Configure wireless network interfaces |
| [`ss`](networking.md#ss) | Display socket statistics, replacement for netstat |
| [`arp`](networking.md#arp) | View or modify the system's ARP cache |
| [`dig`](networking.md#dig) | DNS lookup utility, test DNS name servers |
| [`whois`](networking.md#whois) | Query WHOIS information for domains |
| [`ifplugstatus`](networking.md#ifplugstatus) | Check if network cables are plugged in |
| [`route`](networking.md#route) | Show/manipulate IP routing table |
| [`nmap`](networking.md#nmap) | Network exploration tool and security scanner |
| [`tcpdump`](networking.md#tcpdump) | Capture and analyze network traffic |
| [`nc`](networking.md#nc) | Netcat - Swiss army knife for TCP/IP |
| [`scp`](networking.md#scp) | Securely copy files between hosts |
| [`rsync`](networking.md#rsync) | Fast, versatile file copying and synchronization |
| [`iptables`](networking.md#iptables) | Configure IP packet filter rules |
| [`netcat`](networking.md#netcat) | Read and write data across network connections |
| [`host`](networking.md#host) | DNS lookup utility |

### System Level Commands
[View detailed system commands guide](system.md)

| Command | Description |
|---------|-------------|
| [`uname`](system.md#uname) | Display system information including kernel version |
| [`uptime`](system.md#uptime) | Show how long the system has been running |
| [`date`](system.md#date) | Display or set system date and time |
| [`who`](system.md#who) | Show who is logged on |
| [`whoami`](system.md#whoami) | Print effective user ID |
| [`which`](system.md#which) | Locate a command in system PATH |
| [`id`](system.md#id) | Print user and group information |
| [`sudo`](system.md#sudo) | Execute a command as another user (typically root) |
| [`shutdown`](system.md#shutdown) | Bring the system down safely |
| [`reboot`](system.md#reboot) | Restart the system |
| [`apt`](system.md#apt) | Package management for Debian-based systems |
| [`yum`](system.md#yum) | Package management for older RHEL-based systems |
| [`dnf`](system.md#dnf) | Next generation package management for RHEL-based systems |
| [`pacman`](system.md#pacman) | Package management for Arch Linux |
| [`portage`](system.md#portage) | Package management for Gentoo Linux |

### User & Group Management Commands
[View detailed user management guide](user-and-group-management.md)

| Command | Description |
|---------|-------------|
| [`sudo`](user-and-group-management.md#sudo) | Execute commands with superuser privileges |
| [`useradd`](user-and-group-management.md#useradd) | Create a new user account |
| [`whoami`](user-and-group-management.md#whoami) | Display current user name |
| [`su`](user-and-group-management.md#su) | Switch to another user account |
| [`passwd`](user-and-group-management.md#passwd) | Change user password |
| [`userdel`](user-and-group-management.md#userdel) | Delete a user account |
| [`groupadd`](user-and-group-management.md#groupadd) | Create a new group |
| [`gpasswd`](user-and-group-management.md#gpasswd) | Administer groups |
| [`groupdel`](user-and-group-management.md#groupdel) | Delete a group |

### File Permission Commands
[View detailed file permissions guide](file-permissions.md)

| Command | Description |
|---------|-------------|
| [`ls`](file-permissions.md#ls) | List directory contents with permissions |
| [`chmod`](file-permissions.md#chmod) | Change file mode/permissions |
| [`chown`](file-permissions.md#chown) | Change file owner and group |
| [`chgrp`](file-permissions.md#chgrp) | Change group ownership |
| [`umask`](file-permissions.md#umask) | Set default permissions mask |

### Compression Commands
[View detailed compression commands guide](compression.md)

| Command | Description |
|---------|-------------|
| [`zip`](compression.md#zip) | Package and compress files |
| [`gzip`](compression.md#gzip) | Compress files using Lempel-Ziv coding |
| [`gunzip`](compression.md#gunzip) | Decompress files compressed with gzip |
| [`tar`](compression.md#tar) | Tape archiving utility |
| [`untar`](compression.md#untar) | Extract files from tar archive |

### Pro Linux Commands
[View detailed pro Linux commands guide](pro-linux-commands.md)

| Command | Description |
|---------|-------------|
| [`awk`](pro-linux-commands.md#awk) | Pattern scanning and text processing language |
| [`sed`](pro-linux-commands.md#sed) | Stream editor for filtering and transforming text |
| [`grep`](pro-linux-commands.md#grep) | Search text patterns using regular expressions |






