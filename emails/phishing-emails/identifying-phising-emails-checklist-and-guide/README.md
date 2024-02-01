# 🐡 Identifying Phising Emails CheckList and Guide

```bash
#1 Subject Line
Subject Line of something you might want to click 
or something you dont recall
#2 Recipient Address
Unusual email recipient address
#3 Sender Email and Details
Check if there is something off
Sender details doesn't match sender's address
Typos
#4 Source Code
Check source code
#5 Links
The link uses URL shortening services
There is an image in the source code but it hasn't loaded
#Content
Urgency
Typos
Expiring Date (Urgency)
Attachments

#Do not
Do not Click on enable editing if you have downloaded the file
```



## TryHackMe's CheckList for Investigating the email

```bash
From the email header:

Sender email address
Sender IP address
Reverse lookup of the sender IP address
Email subject line
Recipient email address (this information might be in the CC/BCC field)
Reply-to email address (if any)
Date/time
Afterward, we draw our attention to the email body and attachment(s) (if any).

From the email body:

Any URL links (if an URL shortener service was used, then we'll need to obtain the real URL link)
The name of the attachment
The hash value of the attachment (hash type MD5 or SHA256, preferably the latter)
```

### **How typosquatting works**

{% embed url="https://www.csoonline.com/article/570173/what-is-typosquatting-a-simple-but-effective-attack-technique.html" %}

Threat actors can impersonate domains using:

* A common misspelling of the target domain (CSOnline.com rather than CSOOnline.com, for example)
* A different top-level domain (using .uk rather than .co.uk)
* Combining related words into the domain (CSOOnline-Cybersecurity.com)
* Adding periods to the URL (CSO.Online.com)
* Using similar looking letters to hide the false domain (ÇSÓOnliné.com)
