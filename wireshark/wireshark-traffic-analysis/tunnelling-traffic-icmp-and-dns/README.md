# Tunnelling Traffic: ICMP and DNS

Traffic tunnelling is transferring the data/resources in a secure method to network segments and zones. There is an encapsulation process to hide the data, so the transferred data appear natural for the case, but it contains private data packets and transfers them to the final destination securely.

## ICMP Analysis

ICMP is designed for diagnosing and reporting network communication issues. Sometimes it is used for denial of service (DoS) attacks; also, adversaries use it in data exfiltration and C2 tunnelling activities.

Usually, ICMP tunnelling attacks are anomalies appearing/starting after a malware execution or vulnerability exploitation. **`As the ICMP packets can transfer an additional data payload, adversaries use this section to exfiltrate data and establish a C2 connection..`` `**<mark style="color:yellow;">**`It could be a TCP, HTTP or SSH data.`**</mark>

<mark style="color:yellow;">**`A large volume of ICMP traffic or anomalous packet sizes are indicators of ICMP tunnelling.`**</mark>

| Notes                                                                                                                                                                                   | Wireshark filters                                     |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| Global search                                                                                                                                                                           | <ul><li><code>icmp</code></li></ul>                   |
| <p>"ICMP" options for grabbing the low-hanging fruits:</p><ul><li>Packet length.</li><li>ICMP destination addresses.<br></li><li>Encapsulated protocol signs in ICMP payload.</li></ul> | <ul><li><code>data.len > 64 and icmp</code></li></ul> |



## DNS Analysis

Domain Name System (DNS) is designed to translate/convert IP domain addresses to IP addresses

Similar to ICMP tunnels, DNS attacks are anomalies appearing/starting after a malware execution or vulnerability exploitation. Adversary creates (or already has) a domain address and configures it as a C2 channel. The malware or the commands executed after exploitation sends DNS queries to the C2 server. However, these queries are longer than default DNS queries and crafted for subdomain addresses. Unfortunately, these subdomain addresses are not actual addresses; they are encoded commands as shown below:

"encoded-commands.maliciousdomain.com"

| Notes                                                                                                                                                                                                                                                                                                                                                                                                           | Wireshark Filter                                                                                                   |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Global search                                                                                                                                                                                                                                                                                                                                                                                                   | <ul><li><code>dns</code></li></ul>                                                                                 |
| <p>"DNS" options for grabbing the low-hanging fruits:</p><ul><li>Query length.</li><li>Anomalous and non-regular names in DNS addresses.</li><li>Long DNS addresses with encoded subdomain addresses.</li><li>Known patterns like dnscat and dns2tcp.</li><li>Statistical analysis like the anomalous volume of DNS requests for a particular target.</li></ul><p>!mdns: Disable local link device queries.</p> | <ul><li><code>dns contains "dnscat"</code></li></ul><ul><li><code>dns.qry.name.len > 15 and !mdns</code></li></ul> |
