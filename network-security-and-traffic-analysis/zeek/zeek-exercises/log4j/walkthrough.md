# Walkthrough

```bash
#Commands
zeek -Cr log4shell.pcapng detection-log4j.zeek 
cat http.log | zeek-cut user_agent
cat signatures.log | zeek-cut sig_id | wc -l
```

\
Investigate the log4shell.pcapng file with detection-log4j.zeek script. Investigate the signature.log file. What is the number of signature hits?&#x20;

&#x20;<mark style="color:green;">3</mark>

<figure><img src="https://camo.githubusercontent.com/98ff779686d6f936bf75c81a2a08366c341def9dbd11af6f0d50cfce270f4626/68747470733a2f2f692e696d6775722e636f6d2f5871384c7364592e706e67" alt=""><figcaption></figcaption></figure>

```bash
#You can also check it with this command
cat signatures.log | zeek-cut sig_id | wc -l
```



Investigate the http.log file. Which tool is used for scanning?

<mark style="color:green;">nmap</mark>

<figure><img src="https://camo.githubusercontent.com/2f15cccdc57e60d2d9b1888d9a6a3c933ddaa2c3d2c1e4ac8a1171264a70041c/68747470733a2f2f692e696d6775722e636f6d2f6f7954424973712e706e67" alt=""><figcaption></figcaption></figure>

Investigate the http.log file. What is the extension of the exploit file?

&#x20;<mark style="color:green;">.class</mark>

<figure><img src="https://camo.githubusercontent.com/b3d4910282e1dec0b4ba283cff353105be48dd99eb23a6cca26dbb7d45bb00d7/68747470733a2f2f692e696d6775722e636f6d2f644672623166472e706e67" alt=""><figcaption></figcaption></figure>

Investigate the log4j.log file. Decode the base64 commands. What is the name of the created file?\
<mark style="color:green;">pwned</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/650cb23d284b54bb5857c23dbd1034a0b74706285f7c70a9103673664ea0c221/68747470733a2f2f692e696d6775722e636f6d2f7246724b324c542e706e67" alt=""><figcaption></figcaption></figure>

<figure><img src="https://camo.githubusercontent.com/af85d1cc23b1d7d640c1deb959b634c12fc3bd003eccf58ff515ebe70b9a43ba/68747470733a2f2f692e696d6775722e636f6d2f3839527177597a2e706e67" alt=""><figcaption></figcaption></figure>

```bash
#unnecessary to use all what I used 
cat log4j.log | grep -e "Base64"
```

\
