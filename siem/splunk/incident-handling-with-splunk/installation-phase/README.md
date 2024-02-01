# Installation Phase

**Installation Phase**

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/de0578c67c4b14c280f01fe9a4090ea5.png" alt=""><figcaption></figcaption></figure>

Once the attacker has successfully exploited the security of a system, he will try to install a backdoor or an application for persistence or to gain more control of the system. This activity comes under the installation phase.

In the previous Exploitation phase, we found evidence of the webserver `iamreallynotbatman.com` getting compromised via brute-force attack by the attacker using the python script to automate getting the correct password. The attacker used the IP" for the attack and the IP to log in to the server. This phase will investigate any payload / malicious program uploaded to the server from any attacker's IPs and installed into the compromised server.

To begin an investigation, we first would narrow down any http traffic coming into our server 192.168.250.70 containing the term ".exe." This query may not lead to the findings, but it's good to start from 1 extension and move ahead.

**Search Query**: `index=botsv1 sourcetype=stream:http dest_ip="192.168.250.70" *.exe`

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/4097da92bb83bd61cdacec4539c58d67.gif" alt=""><figcaption></figcaption></figure>

With the search query in place, we are looking for the fields that could have some values of our interest. As we could not find the file name field, we looked at the missing fields and saw a field. `part_filename{}`.

Observing the interesting fields and values, we can see the field `part_filename{}` contains the two file names. an executable file `3791.exe` and a PHP file `agent.php`

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/f2206e28fac1af4e5033d1eb7cd7f29d.png" alt=""><figcaption></figcaption></figure>

Next, we need to find if any of these files came from the IP addresses that were found to be associated with the attack earlier.

Click on the file name; it will be added to the search query, then look for the field c\_ip, which seems to represent the client IP.

**Search Query:**`index=botsv1 sourcetype=stream:http dest_ip="192.168.250.70" "part_filename{}"="3791.exe"`

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/e8f2b1f9924e74acaf2224cd7c13f6f6.png" alt=""><figcaption></figcaption></figure>

**Was this file executed on the server after being uploaded?**

We have found that file 3791.exe was uploaded on the server. The question that may come to our mind would be, was this file executed on the server? We need to narrow down our search query to show the logs from the host-centric log sources to answer this question.

**Search Query:** `index=botsv1 "3791.exe"`

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/2dd77a76ba3366bf822576b7600d4669.png" alt=""><figcaption></figcaption></figure>

Following the Host-centric log, sources were found to have traces of the executable 3791. exe.

* Sysmon
* WinEventlog
* fortigate\_utm

For the evidence of execution, we can leverage sysmon and look at the EventCode=1 for program execution.

Reference: [https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon)

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/0135d57671ea197866054124115cfb4c.png" alt=""><figcaption></figcaption></figure>

**Search Query:** `index=botsv1 "3791.exe" sourcetype="XmlWinEventLog" EventCode=1`

Query Explanation: This query will look for the process Creation logs containing the term "3791.exe" in the logs.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/140a87acbf87ae7b9cf62f41dd93acdb.png" alt=""><figcaption></figcaption></figure>

Looking at the output, we can clearly say that this file was executed on the compromised server. We can also look at other host-centric log sources to confirm the result.
