# Walkthrough

<pre class="language-bash"><code class="lang-bash">#Commands
zeek -Cr phishing.pcap file-extract-demo.zeek
cat dns.log | zeek-cut id.orig_h id.resp_h query qtype_name | head -n 15
<strong>cat files.log | zeek-cut mime_type md5 sha1 sha256
</strong>cat http.log | zeek-cut host  resp_mime_types
cat http.log | zeek-cut uri

</code></pre>

Investigate the logs. What is the suspicious source address? Enter your answer in defanged format.

<mark style="color:green;">10\[.]6\[.]27\[.]102</mark>

<figure><img src="https://camo.githubusercontent.com/30d12b7c37b04669dc8195c986ca677c44ee1f8e4e81cfd840c5efa42059fbb6/68747470733a2f2f692e696d6775722e636f6d2f787465336c33472e706e67" alt=""><figcaption></figcaption></figure>

Investigate the http.log file. Which domain address were the malicious files downloaded from? Enter your answer in defanged format.

<mark style="color:green;">smart-fax\[.]com</mark>

<figure><img src="https://camo.githubusercontent.com/bb8e1409d4993ec062f5e483c8a3ebb3cce3627f6eb854722e7ee53e3d796f57/68747470733a2f2f692e696d6775722e636f6d2f35724f4f5261792e706e67" alt=""><figcaption></figcaption></figure>

Investigate the malicious document in VirusTotal. What kind of file is associated with the malicious document?

<mark style="color:green;">VBA</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/acf81bf566d70fbc0d1b5c827b3050c51d6d150cc23ccf2c83f8f968c75640d5/68747470733a2f2f692e696d6775722e636f6d2f75617a4a3552632e706e67" alt=""><figcaption></figcaption></figure>

Now with the hashes i can go to Virus Total and look for more information

<figure><img src="https://camo.githubusercontent.com/bb8093a2f073c6ece3288eba6906346ae053345fb74e2215e3927d7837a54241/68747470733a2f2f692e696d6775722e636f6d2f756877657957342e706e67" alt=""><figcaption><p>the answer is VBA but It has changed I don't know why, i had to look for this one</p></figcaption></figure>

Investigate the extracted malicious .exe file. What is the given file name in Virustotal?\
<mark style="color:green;">PleaseWaitWindow.exe</mark>

<figure><img src="https://camo.githubusercontent.com/d506dd0d09cd41a256f1637463ee6c1bb8233a909680f074faee46bb25117000/68747470733a2f2f692e696d6775722e636f6d2f34626a705469342e706e6767" alt=""><figcaption></figcaption></figure>

Investigate the malicious .exe file in VirusTotal. What is the contacted domain name? Enter your answer in defanged format.\
<mark style="color:green;">hopto\[.]org</mark>

&#x20;[![](https://camo.githubusercontent.com/04f5223afdc2f9081a540fd074c36163f8253f2ea1c5b3e497c689ac4173431b/68747470733a2f2f692e696d6775722e636f6d2f77425048714b482e706e67)](https://camo.githubusercontent.com/04f5223afdc2f9081a540fd074c36163f8253f2ea1c5b3e497c689ac4173431b/68747470733a2f2f692e696d6775722e636f6d2f77425048714b482e706e67)



Investigate the http.log file. What is the request name of the downloaded malicious .exe file?

<mark style="color:green;">knr.exe</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/6815b9cf559d1fedc5952832c6fffd64d8dff532262f7fb3154fa9f4f85ce789/68747470733a2f2f692e696d6775722e636f6d2f70326e507333382e706e67" alt=""><figcaption></figcaption></figure>
