# Weaponization

Weaponization

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/66ab36ee8b80a54b106b069cae10f89c.png" alt=""><figcaption></figcaption></figure>

In the weaponization phase, the adversaries would:

* Create Malware / Malicious document to gain initial access / evade detection etc.
* Establish domains similar to the target domain to trick users.
* Create a Command and Control Server for the post-exploitation communication/activity etc.

We have found some domains / IP addresses associated with the attacker during the investigations. This task will mainly look into OSINT sites to see what more information we can get about the adversary.\


\


So far, we have found a domain `prankglassinebracket.jumpingcrab.com` associated with this attack. Our first task would be to find the IP address tied to the domains that may potentially be pre-staged to attack Wayne Enterprise.

In the following exercise, we will be searching the online Threat Intel sites for any information like IP addresses/domains / Email addresses associated with this domain which could help us know more about this adversary.\


Robtex:\
[Robtex](https://www.robtex.com/) is a Threat Intel site that provides information about IP addresses, domain names, etc.\


Please search for the domain on the robtex site and see what we get. We will get the IP addresses associated with this domain.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/7ad2296f02b00a73a3ae2e4182fa7cfc.png" alt=""><figcaption></figcaption></figure>

Some domains/subdomains associated with this domain:

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/c6aa355d30ed9425cd6e923526a03d46.png" alt=""><figcaption></figcaption></figure>

Reference: [https://www.robtex.com/dns-lookup/prankglassinebracket.jumpingcrab.com](https://www.robtex.com/dns-lookup/prankglassinebracket.jumpingcrab.com)

Next, search for the IP address `23.22.63.114`  on this Threat Intel site.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/2a9dd066e2b6ef2cd55a5e0c04983776.png" alt=""><figcaption></figcaption></figure>

What did we find? this IP is associated with some domains that look pretty similar to the WAYNE Enterprise site.\


Reference: [https://www.robtex.com/ip-lookup/23.22.63.114](https://www.robtex.com/ip-lookup/23.22.63.114)

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/87794e9d70b8b0dac729232443427181.png" alt=""><figcaption></figcaption></figure>

\


Virustotal

[Virustotal](https://www.virustotal.com/) is an OSINT site used to analyze suspicious files, domains, IP, etc. Let's now search for the IP address on the virustotal site. If we go to the RELATIONS tab, we can see all the domains associated with this IP which look similar to the Wayn Enterprise company.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/b217030ec313023a8d811ad513a28378.png" alt=""><figcaption></figcaption></figure>

In the domain list, we saw the domain that is associated with the attacker`www.po1s0n1vy.com` . Let us search for this domain on the virustotal.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/0d1024a79200a34705ac77b986782104.png" alt=""><figcaption></figcaption></figure>

We can also look for the whois information on this site -> [whois.domaintools.com](https://whois.domaintools.com/) to see if we can find something valuable.

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/a306319398fa56470363ca0f41cd814f.png)
