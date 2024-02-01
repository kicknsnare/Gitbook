# Delivery Phase

Delivery\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/cbc524d15fd41900361c2ca2789cbfe7.png" alt=""><figcaption></figcaption></figure>

Attackers create malware and infect devices to gain initial access or evade defenses and find ways to deliver it through different means. We have identified various IP addresses, domains and Email addresses associated with this adversary. Our task for this lesson would be to use the information we have about the adversary and use various Threat Hunting platforms and OSINT sites to find any malware linked with the adversary.\


Threat Intel report suggested that this adversary group Poison lvy appears to have a secondary attack vector in case the `initial compromise` fails. Our objective would be to understand more about the attacker and their methodology and correlate the information found in the logs with various threat Intel sources.

**OSINT sites**

* Virustotal
* ThreatMiner
* Hybrid-Analysis

**ThreatMiner**

Let's start our investigation by looking for the IP `23.22.63.114` on the Threat Intel site [ThreatMiner.](https://www.threatminer.org/host.php?q=23.22.63.114#gsc.tab=0\&gsc.q=23.22.63.114\&gsc.page=1)

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/994b52e66e64ffba61ca57d32ace6a54.png" alt=""><figcaption></figcaption></figure>

We found three files associated with this IP, from which one file with the hash value  `c99131e0169171935c5ac32615ed6261` seems to be malicious and something of interest.

Now, click on this MD5 hash value to see the metadata and other important information about this particular file.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/511a309aacc571f2176931686df681e0.png" alt=""><figcaption></figcaption></figure>

Reference: [https://www.threatminer.org/host.php?q=23.22.63.114#gsc.tab=0\&gsc.q=23.22.63.114\&gsc.page=1](https://www.threatminer.org/host.php?q=23.22.63.114#gsc.tab=0\&gsc.q=23.22.63.114\&gsc.page=1)

**Virustotal**

Open [virustotal.com](http://virustotal.com/) and search for the hash on the virustotal now. Here, we can get information about the metadata about this Malware in the Details tab.

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/c380913c90e52016683cbcfe9174b35e.png)

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/8edbbf929731d7718587d3c1adc66648.png" alt=""><figcaption></figcaption></figure>

Reference: [https://www.virustotal.com/gui/file/9709473ab351387aab9e816eff3910b9f28a7a70202e250ed46dba8f820f34a8/community](https://www.virustotal.com/gui/file/9709473ab351387aab9e816eff3910b9f28a7a70202e250ed46dba8f820f34a8/community)

**Hybrid-Analysis**

Hybrid Analysis is a beneficial site that shows the behavior Analysis of any malware. Here you can look at all the activities performed by this Malware after being executed. Some of the information that Hybrid-Analysis provides are:

* Network Communication.
* DNS Requests
* Contacted Hosts with Country Mapping
* Strings
* MITRE ATT\&CK Mapping
* Malicious Indicators.
* DLLs Imports / Exports
* Mutex Information if created
* File Metadata
* Screenshots

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/6ef05247bb5c92e91d0a2894f219758a.png" alt=""><figcaption></figcaption></figure>

Scroll down, and you will get a lot of information about this Malware.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/7a714d6ca3a44c0c570c45cb2711b660.png" alt=""><figcaption></figcaption></figure>

Reference**:** [https://www.hybrid-analysis.com/sample/9709473ab351387aab9e816eff3910b9f28a7a70202e250ed46dba8f820f34a8?environmentId=100](https://www.hybrid-analysis.com/sample/9709473ab351387aab9e816eff3910b9f28a7a70202e250ed46dba8f820f34a8?environmentId=100)
