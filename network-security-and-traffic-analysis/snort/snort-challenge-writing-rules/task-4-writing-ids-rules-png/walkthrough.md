# Walkthrough

[https://gist.github.com/leommoore/f9e57ba2aa4bf197ebc5](https://gist.github.com/leommoore/f9e57ba2aa4bf197ebc5)

{% embed url="https://en.wikipedia.org/wiki/List_of_file_signatures" %}

```bash
#Commands that I used:
snort -c local.rules -A full -l . -r ftp-png-gif.pcap
sudo strings ftp-png-gif.pcap
###IMPORTANT###
snort -d -r <snort_log>
#For this command you will use snort and get the same answers as with strings
```

**`Let's create IDS Rules for PNG files in the traffic!Answer the questions below`**

Navigate to the task folder.

Use the given pcap file.

**`Write a rule to detect the PNG file in the given pcap.`**

Investigate the logs and identify the software name embedded in the packet.



For this one I had to search for the signature of PNG files to make a filter with 'content'

```bash
#New things
|89 50 4E 47 0D 0A 1A 0A| -> png signature
depth:8 -> #Will limit the search of the packet 
#for the first 8 bytes corresponding to the png signature
```

&#x20;

<figure><img src="https://camo.githubusercontent.com/d7fec352bf5f92badd55df05a41c6484f7c329f5b1f16120912500590cd53eec/68747470733a2f2f692e696d6775722e636f6d2f5370354f71384a2e706e67" alt=""><figcaption></figcaption></figure>

&#x20;[![](https://camo.githubusercontent.com/2318b127e87967ec06c2eb0289785af1a70697727bcd44177bf06c40f2e03bdd/68747470733a2f2f692e696d6775722e636f6d2f317131764276442e706e67)](https://camo.githubusercontent.com/2318b127e87967ec06c2eb0289785af1a70697727bcd44177bf06c40f2e03bdd/68747470733a2f2f692e696d6775722e636f6d2f317131764276442e706e67)

```bash
sudo strings ftp-png-gif.pcap
```

[![](https://camo.githubusercontent.com/dc5ce9c40662a8b3bd6de542285ed14dcfd562e21882024a9c6f374b4f38c352/68747470733a2f2f692e696d6775722e636f6d2f6d593367575a672e706e67)](https://camo.githubusercontent.com/dc5ce9c40662a8b3bd6de542285ed14dcfd562e21882024a9c6f374b4f38c352/68747470733a2f2f692e696d6775722e636f6d2f6d593367575a672e706e67)

<mark style="color:yellow;">Adobe Image</mark>&#x20;

Clear the previous log and alarm files.

Deactivate/comment on the old rule.

**`Write a rule to detect the GIF file in the given pcap.`**

Investigate the logs and identify the image format embedded in the packet.

```bash
#I tried my way but something was off so I looked for other ways
```



<figure><img src="https://camo.githubusercontent.com/3d00769eaabb886a82a9fd198a79e003ae1a09f52372d52c7282c8fbf84d56a5/68747470733a2f2f692e696d6775722e636f6d2f42303366736a632e706e67" alt=""><figcaption></figcaption></figure>

<figure><img src="https://camo.githubusercontent.com/2845435614edd871d05291dc7b3328444a522598ae4a83294dfbc4e93f619cf3/68747470733a2f2f692e696d6775722e636f6d2f6b3331666650312e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/80058afac1552b7d58b4307c9caec25e35e25ff17b66f08e942965dfb1306097/68747470733a2f2f692e696d6775722e636f6d2f304e6a6b5073512e706e67" alt=""><figcaption></figcaption></figure>

<mark style="color:yellow;">GIF89a</mark>
