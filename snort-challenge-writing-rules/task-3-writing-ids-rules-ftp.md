# Task 3 Writing IDS Rules FTP

```bash
#commands that I used:
snort -c local.rules -A full -l . -r <file>
sudo strings <snort_log> | grep 220 | head
```

Navigate to the task folder.

Use the given pcap file.

**`Write rules to detect "all TCP port 21"  traffic in the given pcap.`**

What is the number of detected packets?

&#x20;<mark style="color:yellow;">614</mark>

<figure><img src="https://camo.githubusercontent.com/f3bf0b9b3a1634b78d43fcef732cb836b83520f25a98912b138f3a3455248b9a/68747470733a2f2f692e696d6775722e636f6d2f4d4c4d635a454e2e706e67" alt=""><figcaption></figcaption></figure>

<figure><img src="https://camo.githubusercontent.com/ace4e61baacb1ccd4e4226a80e27e39709e124bc9ed0506211c6287fa96688e6/68747470733a2f2f692e696d6775722e636f6d2f33505a72795a442e706e67" alt=""><figcaption></figcaption></figure>

Investigate the log file.

What is the FTP service name?

<mark style="color:yellow;">Microsoft FTP Service</mark>

&#x20;

```bash
sudo strings <snort_log> | grep 220 | head
```

&#x20;For this one I had to do some research. 220 signifies a succesful response and indicates that the FTP server is ready for a new user to authenticate or initiate

<figure><img src="https://camo.githubusercontent.com/d623cbd4e7b696c280d626574b4c35c5cabd6b86bb911f9741dcad3ff44cfde8/68747470733a2f2f692e696d6775722e636f6d2f4f36546a6e37442e706e67" alt=""><figcaption></figcaption></figure>

Clear the previous log and alarm files.

Deactivate/comment on the old rules.

**`Write a rule to detect failed FTP login attempts in the given pcap.`**\


What is the number of detected packets?

<mark style="color:yellow;">41</mark>

<figure><img src="https://camo.githubusercontent.com/03e3b48b12a93cc952a06e5fcc97ddfef336fd7772b67c16012744b3ff563e4a/68747470733a2f2f692e696d6775722e636f6d2f6b4179663554532e706e67" alt=""><figcaption></figcaption></figure>

<figure><img src="https://camo.githubusercontent.com/b7cb94ff2954fff08d77e1e3811d4f946c188d9d9e9ac2cb469586e760032a3c/68747470733a2f2f692e696d6775722e636f6d2f7255654754774b2e706e67" alt=""><figcaption></figcaption></figure>

Clear the previous log and alarm files.

Deactivate/comment on the old rule.

**`Write a rule to detect successful FTP logins in the given pcap.`**

What is the number of detected packets?

<mark style="color:yellow;">1</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/352d509de551167b19e0540db6189f9e639e158b273dfbb80788c1e02b06f6ab/68747470733a2f2f692e696d6775722e636f6d2f47626a704a336e2e706e67" alt=""><figcaption></figcaption></figure>

<figure><img src="https://camo.githubusercontent.com/3879ddf43aa7c5256961d2d690a4424047a5b328fb311a417b66cde664723096/68747470733a2f2f692e696d6775722e636f6d2f6566675771725a2e706e67" alt=""><figcaption></figcaption></figure>

Clear the previous log and alarm files.

Deactivate/comment on the old rule.

**`Write a rule to detect failed FTP login attempts with a valid username but a bad password or no password.`**

What is the number of detected packets?

<mark style="color:yellow;">42</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/fd63b5a06e1acdcd394a604ced0f03f9418add78d629131f23064e3e0b482fb2/68747470733a2f2f692e696d6775722e636f6d2f357a63364b754a2e706e67" alt=""><figcaption></figcaption></figure>

&#x20;[![](https://camo.githubusercontent.com/4ca7e02ce8a67f42f869e02d59c5be13a2f566cf4bc23061037738ea6e90e4ad/68747470733a2f2f692e696d6775722e636f6d2f526a43584c54492e706e67)](https://camo.githubusercontent.com/4ca7e02ce8a67f42f869e02d59c5be13a2f566cf4bc23061037738ea6e90e4ad/68747470733a2f2f692e696d6775722e636f6d2f526a43584c54492e706e67)

Clear the previous log and alarm files.

Deactivate/comment on the old rule.

**`Write a rule to detect failed FTP login attempts with "Administrator" username but a bad password or no password.`**

What is the number of detected packets?

<mark style="color:yellow;">7</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/1a6ba9c9f738135a7820f3f0ca7bacb50ef9b23641a084370fae3604a3429362/68747470733a2f2f692e696d6775722e636f6d2f6c4b53473763502e706e67" alt="" width="563"><figcaption></figcaption></figure>

&#x20;[![](https://camo.githubusercontent.com/5d2fce87a746026b98f365c9fe1cc24e159c5a6ff3268095e9341db5c8dcf4d9/68747470733a2f2f692e696d6775722e636f6d2f63526c535955782e706e67)](https://camo.githubusercontent.com/5d2fce87a746026b98f365c9fe1cc24e159c5a6ff3268095e9341db5c8dcf4d9/68747470733a2f2f692e696d6775722e636f6d2f63526c535955782e706e67)
