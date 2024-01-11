# Filters



## Last Update 1/10/2024

{% embed url="https://app.gitbook.com/o/aeFeXGlefIRFJAt4D2zG/s/YEchRCx098G4mQw5r5r0/wireshark/wireshark-101/filtering-captures" %}

{% embed url="https://www.wireshark.org/docs/wsug_html_chunked/ChWorkBuildDisplayFilterSection.html" %}

## Operators

* <mark style="color:blue;">and - operator</mark>: **`and / &&`**
* <mark style="color:blue;">or - operator</mark>: **`or / ||`**
* <mark style="color:blue;">equals - operator:</mark> **`eq / ==`**
* <mark style="color:blue;">not equal - operator:</mark> **`ne / !=`**
* <mark style="color:blue;">greater than - operator:</mark> **`gt /  >`**
* <mark style="color:blue;">less than - operator:</mark> **`lt / <`**

## Basic Filtering

The basic syntax of Wireshark filters is some kind of service or protocol like ip or tcp, followed by a dot then whatever is being filtered for example an address, MAC, SRC, protocol, etc.

```bash
#IP
ip.addr == <IP Address>
#Filtering by SRC and DST:
ip.src == <SRC IP Address> and ip.dst == <DST IP Address> 
#Filtering by TCP Protocols:
tcp.port == <Port NUM> or <Protocol Name>
#Filtering by UDP Protocols:
udp.port == <Port NUM> or <Protocol Name>
#Filtering by packet number
frame.number== <number>
#ARP 1= request 2= reply
arp.opcode== 1 | arp.opcode == 2
#MAC address
eth.src == <MAC> 
eth.dst == <MAC>
eth.addr == <MAC>
```

```bash
####################################################################
IP FILTERS
####################################################################
#Show all IP packets.
ip
#Show all packets containing IP address 10.10.10.111.
ip.addr == 10.10.10.111
#Show all packets containing IP addresses from 10.10.10.0/24 subnet.
ip.addr == 10.10.10.0/24
#Show all packets originated from 10.10.10.111
ip.src == 10.10.10.111
#Show all packets sent to 10.10.10.111
ip.dst == 10.10.10.111
#TTL
ip.ttl...

```

```bash
##################################################################
TCP and UDP Filters
##################################################################
#Show all TCP/UDP packets with port 80 
tcp.port == 80 | udp.port == 53
#Show all TCP/UDP packets originating from port 1234
tcp.srcport == 1234 | udp.srcport == 1234
#Show all TCP/UDP packets sent to port 80
tcp.dstport == 80 | udp.dstport == 5353

```

```bash
###############################################################
Application Level Protocol Filters | HTTP and DNS
################################################################
#Show all HTTP packets
http
#how all packets with HTTP response code "200"
http.response.code == 200
#Show all HTTP GET requests
http.request.method == "GET"
#Show all HTTP POST requests
http.request.method == "POST"
#http and port filter example
http.request.method == "GET" and tcp.port== 80
#Show all DNS packets
dns
#Show all DNS requests
dns.flags.response == 0
#Show all DNS responses
dns.flags.response == 1
#Show all DNS "A" records    
dns.qry.type == 1
```

## Advanced Filtering

```bash
#Contain Filter
http.server contains "Apache" <- Keyword
#Matches Filter (it is case insensitive)
http.host matches "\.(php|html)" <- regular expression 
#In filter
tcp.port in {80 443 8080} <- scope/range
#filtering port range
udp.dstport >=55 and udp.dstport <=70 #from 55 to 70
#Upper and lower Filter
upper(http.server) contains "APACHE" #Find all "APACHE" servers.
lower(http.server) contains "apache" #Find all "apache" servers.
#String 
string(frame.number) matches "[13579]$" #Find all frames with odd numbers
even == "[02468]$"

```

## Nmap Scans

```bash
#TCP
tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size > 1024 
#SYN
tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size <= 1024  
#UDP
icmp.type==3 and icmp.code==3  
```

## ARP

<pre class="language-bash"><code class="lang-bash"><strong>#ARP 
</strong>arp
#ARP requests
arp.opcode == 1
#ARP responses
arp.opcode == 2
#ARP Scanning
arp.dst.hw_mac==00:00:00:00:00:00
#Possible ARP poisoning detection
arp.duplicate-address-detected or arp.duplicate-address-frame
#Possible ARP flooding from detection:
((arp) &#x26;&#x26; (arp.opcode == 1)) &#x26;&#x26; (arp.src.hw_mac == target-mac-address)
</code></pre>

## DHCP

DHCP Important note:

Due to the nature of the protocol, only "Option 53" ( request type) has predefined static values. You should filter the packet type first, and then you can filter the rest of the options by "applying as column" or use the advanced filters like "contains" and "matches".

<pre class="language-bash"><code class="lang-bash">#DHCP
dhcp or bootp
#DHCP Request -> Host Name Information
dhcp.option.dhcp == 3
######OPTIONS#######
dhcp.option.type== (number)
<strong>-Option 12: #Hostname.
</strong>-Option 50: #Requested IP address.
-Option 51: #Requested IP lease time.
<strong>-Option 61: #Client's MAC address.
</strong>dhcp.option.hostname contains "keyword"
#DHCP ACK -> Accepted Requests
dhcp.option.dhcp == 5
-Option 15: #Domain name.
-Option 51: #Assigned IP lease time.
dhcp.option.domain_name contains "keyword"
#NAK -> Denied Requests
dhcp.option.dhcp == 6 
-Option 56: #Message (rejection details/reason).
</code></pre>

## NetBIOS

```bash
#NetBIOS
nbns
nbns.name contains "keyword"
#Registration Requests
nbns.flags.opcode == 5
```

## Kerberos

```bash
#Kerberos
kerberos
#CNameString: The username.
kerberos.CNameString contains "keyword" 
#To avoid hostname information:
kerberos.CNameString and !(kerberos.CNameString contains "$" )
#pvno: Protocol version
kerberos.pvno == 5
#realm: Domain name for the generated ticket
kerberos.realm contains ".org" 
#addresses: Client IP address and NetBIOS name
kerberos.SNameString == "krbtg"
```

## ICMP

```bash
#ICMP
icmp
data.len > 64 and icmp
```

## DNS

```bash
#DNS
#Show all DNS packets
dns
#Show all DNS requests
dns.flags.response == 0
#Show all DNS responses
dns.flags.response == 1
#Show all DNS "A" records    
dns.qry.type == 1

dns contains "dnscat"

dns.qry.name.len > 15 and !mdns
```

## FTP

<pre class="language-bash"><code class="lang-bash">#FTP
ftp
#x1x series: Information request responses.
ftp.response.code == 
-211: System status.
-212: Directory status.
-213: File status
#x2x series: Connection messages.
ftp.response.code == 
-220: Service ready.
-227: Entering passive mode.
<strong>-228: Long passive mode.
</strong>-229: Extended passive mode.

<strong>#x3x series: Authentication messages.
</strong>ftp.response.code == 
-230: User login.
<strong>-231: User logout.
</strong><strong>-331: Valid username.
</strong>-430: Invalid username or password
-530: No login, invalid password.
#FTP Commands
ftp.request.command ==
<strong>-USER: Username.
</strong>-PASS: Password.
-CWD: Current work directory.
-LIST: List.
ftp.request.arg == "password"
#Bruteforce signal: List failed login attempts.
ftp.response.code == 530
#Bruteforce signal: List target username.
(ftp.response.code == 530) and (ftp.response.arg contains "username")
<strong>#Password spray signal: List targets for a static password.
</strong>(ftp.request.command == "PASS" ) and (ftp.request.arg == "password")

</code></pre>

## HTTP in Detail

<pre class="language-bash"><code class="lang-bash">#HTTP
http
http2
#HTTP Requests methods
http.request.method == "GET"
http.request.method == "POST"
#Listing all requests
http.request
############## HTTP status codes ##############
http.response.code == 
#-301 Moved Permanently: Resource is moved to a new URL/path (permanently).
#-302 Moved Temporarily: Resource is moved to a new URL/path (temporarily).
#-400 Bad Request: Server didn't understand the request.
#-401 Unauthorised: URL needs authorisation (login, etc.).
#-403 Forbidden: No access to the requested URL. 
#-404 Not Found: Server can't find the requested URL.
#-405 Method Not Allowed: Used method is not suitable or blocked.
<strong>#-408 Request Timeout:  Request look longer than server wait time.
</strong>#-500 Internal Server Error: Request not completed, unexpected error.
#-503 Service Unavailable: Request not completed server or service is down.

############ HTTP Parameters ##############
#-User Agent
http.user_agent contains "nmap"
#-Request Uri
http.request.uri contains "admin"
#-Full Uri
Full *URI: Complete URI information.
#-Server
http.server contains "apache"
#-Host: Hostname of the server
http.host contains "keyword"
#-Connection
http.host == "keyword"
#-Line-based text data
http.connection == "Keep-Alive"
#-HTML Form URL Encoded: Web form information.
data-text-lines contains "keyword"

############# User Agent ################
http.user_agent
(http.user_agent contains "sqlmap") or (http.user_agent contains "Nmap") or (http.user_agent contains "Wfuzz") or (http.user_agent contains "Nikto")


############### Log4j ####################
#The attack starts with POST request
http.request.method == "POST"
#There are known cleartext patterns: "jndi:ldap" and "Exploit.class".
(ip contains "jndi") or ( ip contains "Exploit")
(frame contains "jndi") or ( frame contains "Exploit")
(http.user_agent contains "$") or (http.user_agent contains "==")
</code></pre>

## HTTPS

<pre class="language-bash"><code class="lang-bash">#https
tcp.port == 443
http.request
#TLS: Global TLS search
tls
#TLS Client Request
tls.handshake.type == 1
#TLS Server response
tls.handshake.type == 2
#Local Simple Service Discovery Protocol (SSDP)
# SSDP is a network protocol that provides advertisement and discovery of network services.
ssdp
<strong>#Client Hello:
</strong>(http.request or tls.handshake.type == 1) and !(ssdp) 
#Server Hello:
(http.request or tls.handshake.type == 2) and !(ssdp)  
#Watching encrypted data after uploading the key
http2 
</code></pre>
