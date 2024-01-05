# Walkthrough

<pre class="language-bash"><code class="lang-bash">#Commands that I used
<strong>sudo snort -c local.rules -A console -r ms-17-010.pcap
</strong>sudo snort -c local-1.rules -A full -l . -r ms-17-010.pcap
sudo snort -d -r snort.log.1703850430
sudo strings snort.log.1703850430
</code></pre>

\
Navigate to the task folder.

Use the given pcap file.

**`Use the given rule file (local.rules) to investigate the ms1710 exploitation.`**

What is the number of detected packets?

<mark style="color:yellow;">25154</mark>

&#x20;[![](https://camo.githubusercontent.com/3dc10bc95b0ee60cf7a380c5f8416c40d33cfac2564ae83f50d21dbd0fdc0643/68747470733a2f2f692e696d6775722e636f6d2f696a766a6e33722e706e67)](https://camo.githubusercontent.com/3dc10bc95b0ee60cf7a380c5f8416c40d33cfac2564ae83f50d21dbd0fdc0643/68747470733a2f2f692e696d6775722e636f6d2f696a766a6e33722e706e67)

&#x20;

<figure><img src="https://camo.githubusercontent.com/8866086f1026abfd55ad65a6c8ec7e0a723745748f47fbd01049afb8f2d40f9e/68747470733a2f2f692e696d6775722e636f6d2f7a6154414b44772e706e67" alt=""><figcaption><p>content of local.rules</p></figcaption></figure>

Clear the previous log and alarm files.

Use local-1.rules empty file to write a new rule to detect payloads containing the "\IPC$" keyword.

What is the number of detected packets?

<mark style="color:yellow;">12</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/c80e3e798badec83009028913f300aaa25e5288e1af0eb96aedc696c1e4bd858/68747470733a2f2f692e696d6775722e636f6d2f4e3049533031762e706e67" alt=""><figcaption></figcaption></figure>



Investigate the log/alarm files.

What is the requested path?

<mark style="color:yellow;">192.168.116.138\IPC$</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/20aee00354283de43086a084d4a9c7de95f83800a64a269510439a184187163b/68747470733a2f2f692e696d6775722e636f6d2f3754376d6a68472e706e67" alt=""><figcaption></figcaption></figure>

a [![](https://camo.githubusercontent.com/536b59a4a6db56e5ad9640b802c64b6e86744a06fb035541d4f3336622f36717/68747470733a2f2f692e696d6775722e636f6d2f51366b597447532e706e67)](https://camo.githubusercontent.com/536b59a4a6db56e5ad9640b802c64b6e86744a06fb035541d4f3336622f36717/68747470733a2f2f692e696d6775722e636f6d2f51366b597447532e706e67)

What is the CVSS v2 score of the MS17-010 vulnerability?

<mark style="color:yellow;">9.3</mark>

{% embed url="https://www.tenable.com/plugins/nessus/97737" %}
