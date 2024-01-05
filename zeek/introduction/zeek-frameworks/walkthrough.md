# Walkthrough

```bash
#Commands
zeek -C -r case1.pcap intelligence-demo.zeek 
cat intel.log | zeek-cut seen.where | nl
cat http.log | zeek-cut method host uri | nl
zeek -C -r case1.pcap hash-demo.zeek 
cat files.log | zeek-cut mime_type md5 | nl
zeek -C -r case1.pcap file-extract-demo.zeek
file *| nl


```

\
Investigate the **case1**.pcap file with **intelligence-demo.zeek** script. Investigate the intel.log file. Look at the second finding, where was the intel info found? \
<mark style="color:green;">IN\_HOST\_HEADER</mark>

<figure><img src="https://camo.githubusercontent.com/edc46ae5815a43a66e8b784f9a57924f10c3c335ea897a8633368735fff79f37/68747470733a2f2f692e696d6775722e636f6d2f697a3267346d492e706e67" alt=""><figcaption></figcaption></figure>

Investigate the http.log file. What is the name of the downloaded .exe file?

<mark style="color:green;">knr.exe</mark>

<figure><img src="https://camo.githubusercontent.com/b99b4175d2f01d77b7a1e6cff8844d51f3ce48b7ba33be2e173f48c9a89d1e63/68747470733a2f2f692e696d6775722e636f6d2f7a346f666b44552e706e67" alt=""><figcaption></figcaption></figure>

Investigate the case1.pcap file with hash-demo.zeek script. Investigate the files.log file. What is the MD5 hash of the downloaded .exe file?

<mark style="color:green;">cc28e40b46237ab6d5282199ef78c464</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/77f14994c05e5a08b7b6a275d495baa305d49634ff2a869b104acd6eb6b324bc/68747470733a2f2f692e696d6775722e636f6d2f4d38384d3379672e706e67" alt=""><figcaption></figcaption></figure>

Investigate the case1.pcap file with file-extract-demo.zeek script. Investigate the "extract\_files" folder. Review the contents of the text file. What is written in the file?\
<mark style="color:green;">Microsoft NCSI</mark>

&#x20;\


<figure><img src="https://camo.githubusercontent.com/a19d78230584c00390794288c28adf252642d1b574c39269178c86e6c4a4a46a/68747470733a2f2f692e696d6775722e636f6d2f36774973444e362e706e67" alt=""><figcaption></figcaption></figure>
