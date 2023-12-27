# Important information

Quick summary

<mark style="color:red;">alert/drop/reject</mark> PROTOCOL <mark style="color:purple;">any any <> any any</mark> (<mark style="color:orange;">msg: "YOU CAN CONFIGURE THE MSG AS YOU WANT"</mark><mark style="color:red;">;</mark> <mark style="color:green;">sid 1000001(increase last number as you increment your rules)</mark><mark style="color:red;">;</mark> <mark style="color:yellow;">rev:1 (same here)</mark>)

The primary structure of the snort rule is shown below;

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/58234314551a2962ad5617cb22591a2b.png)

Each rule should have a type of action, protocol, source and destination IP, source and destination port and an option. <mark style="color:green;">Remember, Snort is in passive mode by default. So most of the time, you will use Snort as an IDS. You will need to start</mark> <mark style="color:green;"></mark><mark style="color:green;">**"inline mode" to turn on IPS mode.**</mark>

| The most common actions  | <p></p><ul><li>alert: Generate an alert and log the packet.</li></ul><ul><li>log: Log the packet.</li></ul><ul><li>drop: Block and log the packet.</li></ul><ul><li>reject: Block the packet, log it and terminate the packet session. </li></ul>                                                                                                                                                                                                   |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>Protocol<br></p>      | <p>Protocol parameter identifies the type of the protocol that filtered for the rule.</p><p>Note that Snort2 supports only four protocols filters in the rules (IP, TCP, UDP and ICMP). However, you can detect the application flows using port numbers and options. For instance, if you want to detect FTP traffic, you cannot use the FTP keyword in the protocol field but filter the FTP traffic by investigating TCP traffic on port 21.</p> |



## IP and Port numbers

| IP Filtering                            | <mark style="color:green;">alert icmp 192.168.1.56 any <> any any</mark>  (msg: "ICMP Packet From "; sid: 100001; rev:1;)This rule will create an alert for each ICMP packet originating from the 192.168.1.56 IP address.                                                                                                                                                                          |
| --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>Filter an IP range<br></p>           | <mark style="color:green;">alert icmp 192.168.1.0/</mark><mark style="color:yellow;">24</mark> <mark style="color:green;">any <> any any</mark>  (msg: "ICMP Packet Found"; sid: 100001; rev:1;)This rule will create an alert for each ICMP packet originating from the 192.168.1.0/24 subnet.                                                                                                     |
| <p>Filter multiple IP ranges<br></p>    | <mark style="color:green;">alert icmp</mark> <mark style="color:yellow;">\[192.168.1.0/24, 10.1.1.0/24]</mark> <mark style="color:green;">any <> any any</mark>  (msg: "ICMP Packet Found"; sid: 100001; rev:1;)This rule will create an alert for each ICMP packet originating from the 192.168.1.0/24 and 10.1.1.0/24 subnets.                                                                    |
| <p>Exclude IP addresses/ranges<br></p>  | <p>"negation operator" is used for excluding specific addresses and ports. Negation operator is indicated with "!"</p><p><mark style="color:green;">alert icmp</mark> <mark style="color:yellow;">!192.168.1.0/24 any &#x3C;> any any</mark> (msg: "ICMP Packet Found"; sid: 100001; rev:1;)This rule will create an alert for each ICMP packet not originating from the 192.168.1.0/24 subnet.</p> |
| Port Filtering                          | <mark style="color:green;">alert tcp any any <> any</mark> <mark style="color:yellow;">21</mark>  (msg: "FTP Port 21 Command Activity Detected"; sid: 100001; rev:1;)This rule will create an alert for each TCP packet sent to port 21.                                                                                                                                                            |
| <p>Exclude a specific port<br></p>      | <p><mark style="color:green;">alert tcp any any &#x3C;> any</mark> <mark style="color:yellow;">!21</mark>  (msg: "Traffic Activity Without FTP Port 21 Command Channel"; sid: 100001; rev:1;)<br>This rule will create an alert for each TCP packet not sent to port 21.</p>                                                                                                                        |
| <p>Filter a port range (Type 1)<br></p> | <mark style="color:green;">alert tcp any any <> any</mark> <mark style="color:yellow;">1:1024</mark>   (msg: "TCP 1-1024 System Port Activity"; sid: 100001; rev:1;)This rule will create an alert for each TCP packet sent to ports between 1-1024.                                                                                                                                                |
| <p>Filter a port range (Type 2)<br></p> | <p><mark style="color:green;">alert tcp any any &#x3C;> any</mark> <mark style="color:yellow;">:1024</mark>   (msg: "TCP 0-1024 System Port Activity"; sid: 100001; rev:1;)<br>This rule will create an alert for each TCP packet sent to ports less than or equal to 1024.</p>                                                                                                                     |
| <p>Filter a port range (Type 3)<br></p> | <mark style="color:green;">alert tcp any any <> any</mark> <mark style="color:yellow;">1025:</mark> (msg: "TCP Non-System Port Activity"; sid: 100001; rev:1;)This rule will create an alert for each TCP packet sent to source port higher than or equal to 1025.                                                                                                                                  |
| <p>Filter a port range (Type 4)<br></p> | <mark style="color:green;">alert tcp any any <> any</mark> <mark style="color:yellow;">\[21,23]</mark> (msg: "FTP and Telnet Port 21-23 Activity Detected"; sid: 100001; rev:1;)This rule will create an alert for each TCP packet sent to port 21 and 23.                                                                                                                                          |

\
Direction

The direction operator indicates the traffic flow to be filtered by Snort. The left side of the rule shows the source, and the right side shows the destination.

* \-> Source to destination flow.
* <> Bidirectional flow

Note that there is no "<-" operator in Snort.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/9f7624fafc763e0c7c4e3bd70451367b.png" alt=""><figcaption></figcaption></figure>



## General Rule Options

| Msg                  | <p>The message field is a basic prompt and quick identifier of the rule. Once the rule is triggered, the message filed will appear in the console or log. Usually, the message part is a one-liner that summarises the event.<br></p>                                                                                                                                                                                                                                                                                                                                |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>Sid<br></p>       | <p>Snort rule IDs (SID) come with a pre-defined scope, and each rule must have a SID in a proper format. There are three different scopes for SIDs shown below.</p><ul><li>&#x3C;100: Reserved rules</li><li>100-999,999: Rules came with the build.</li><li>>=1,000,000: Rules created by user.</li></ul><p>Briefly, the rules we will create should have sid greater than 100.000.000. Another important point is; SIDs should not overlap, and each id must be unique. </p>                                                                                       |
| <p>Reference<br></p> | <p>Each rule can have additional information or reference to explain the purpose of the rule or threat pattern. That could be a Common Vulnerabilities and Exposures (CVE) id or external information. Having references for the rules will always help analysts during the alert and incident investigation.<br></p>                                                                                                                                                                                                                                                |
| <p>Rev<br></p>       | <p>Snort rules can be modified and updated for performance and efficiency issues. Rev option help analysts to have the revision information of each rule. Therefore, it will be easy to understand rule improvements. Each rule has its unique rev number, and there is no auto-backup feature on the rule history. Analysts should keep the rule history themselves. Rev option is only an indicator of how many times the rule had revisions.</p><p>alert icmp any any &#x3C;> any any (msg: "ICMP Packet Found"; sid: 100001; reference:cve,CVE-XXXX; rev:1;)</p> |



## Payload Detection Rule Options

Payload Detection Rule Options

| <p>Content<br></p>      | <p>Payload data. It matches specific payload data by ASCII, HEX or both. It is possible to use this option multiple times in a single rule. However, the more you create specific pattern match features, the more it takes time to investigate a packet.</p><p>Following rules will create an alert for each HTTP packet containing the keyword "GET". This rule option is case sensitive!</p><ul><li>ASCII mode - alert tcp any any &#x3C;> any 80  (msg: "GET Request Found"; content:"GET"; sid: 100001; rev:1;)</li><li>HEX mode - alert tcp any any &#x3C;> any 80  (msg: "GET Request Found"; content:"|47 45 54|"; sid: 100001; rev:1;)</li></ul>                                                                                                |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>Nocase<br></p>       | Disabling case sensitivity. Used for enhancing the content searches.alert tcp any any <> any 80  (msg: "GET Request Found"; content:"GET"; nocase; sid: 100001; rev:1;)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| <p>Fast_pattern<br></p> | <p>Prioritise content search to speed up the payload search operation. By default, Snort uses the biggest content and evaluates it against the rules. "fast_pattern" option helps you select the initial packet match with the specific value for further investigation. This option always works case insensitive and can be used once per rule. Note that this option is required when using multiple "content" options. </p><p>The following rule has two content options, and the fast_pattern option tells to snort to use the first content option (in this case, "GET") for the initial packet match.<br></p><p>alert tcp any any &#x3C;> any 80  (msg: "GET Request Found"; content:"GET"; fast_pattern; content:"www";  sid:100001; rev:1;)</p> |

\


## Non-payload Detection Rule options

| ID                | Filtering the IP id field.alert tcp any any <> any any (msg: "ID TEST"; id:123456; sid: 100001; rev:1;)                                                                                                                            |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>Flags<br></p>  | <p>Filtering the TCP flags.</p><ul><li>F - FIN</li><li>S - SYN</li><li>R - RST</li><li>P - PSH</li><li>A - ACK</li><li>U - URG</li></ul><p>alert tcp any any &#x3C;> any any (msg: "FLAG TEST"; flags:S;  sid: 100001; rev:1;)</p> |
| <p>Dsize<br></p>  | <p>Filtering the packet payload size.</p><ul><li>dsize:min&#x3C;>max;</li><li>dsize:>100</li><li>dsize:&#x3C;100</li></ul><p>alert ip any any &#x3C;> any any (msg: "SEQ TEST"; dsize:100&#x3C;>300;  sid: 100001; rev:1;)</p>     |
| <p>Sameip<br></p> | Filtering the source and destination IP addresses for duplication.alert ip any any <> any any (msg: "SAME-IP TEST";  sameip; sid: 100001; rev:1;)                                                                                  |

<mark style="color:yellow;">Remember, once you create a rule, it is a local rule and should be in your "local.rules" file. This file is located under "/etc/snort/rules/local.rules". A quick reminder on how to edit your local rules is shown below.</mark>

```bash
sudo gedit /etc/snort/rules/local.rules
```
