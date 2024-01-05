# Walkthrough

```bash
#After you fix the syntax error run this command
sudo snort -c local-X.rules -r mx-1.pcap -A console
#change the number of the local rule for the one that you want to check
```

\
In this section, you need to fix the syntax errors in the given rule files.&#x20;

You can test each ruleset with the following command structure;

`sudo snort -c local-X.rules -r mx-1.pcap -A console`

Fix the syntax error in local-1.rules file and make it work smoothly.

**`What is the number of the detected packets?`**

&#x20;<mark style="color:yellow;">16</mark>

<figure><img src="https://camo.githubusercontent.com/65a90ce8f9cbdbdb998c374b6c03743d8bf4037a631f5e8681370afa86b74e77/68747470733a2f2f692e696d6775722e636f6d2f375a77303275692e706e67" alt=""><figcaption></figcaption></figure>



Fix the syntax error in **`local-2.rules`** file and make it work smoothly.

**`What is the number of the detected packets?`**

<mark style="color:yellow;">68</mark>

<figure><img src="https://camo.githubusercontent.com/0b2407425ddc46bb3e0e203ccd557840fdb4a61409a349cb3d39f53e5e38c12e/68747470733a2f2f692e696d6775722e636f6d2f485643473978432e706e67" alt=""><figcaption></figcaption></figure>

Fix the syntax error in **`local-3.rules`** file and make it work smoothly.

**`What is the number of the detected packets?`**\
<mark style="color:yellow;">87</mark>

<figure><img src="https://camo.githubusercontent.com/53cd9d5db7e5514534d8dc9410040dcb39157436cd681b9f018224c054212067/68747470733a2f2f692e696d6775722e636f6d2f6c5a616f634c442e706e67" alt=""><figcaption></figcaption></figure>

Fix the syntax error in **`local-4.rules`** file and make it work smoothly.

**`What is the number of the detected packets?`**\
<mark style="color:yellow;">90</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/6ecf1b51ea54ef33aa14672e126c9b84b1f76b7e31782f0bded70b90c1823a88/68747470733a2f2f692e696d6775722e636f6d2f566347646144502e706e67" alt=""><figcaption></figcaption></figure>

Fix the syntax error in **`local-5.rules`** file and make it work smoothly.

**`What is the number of the detected packets?`**\
<mark style="color:yellow;">155</mark>

<figure><img src="https://camo.githubusercontent.com/09e4ac7b1d2334c74ee2dbcb3ac4d93806f8358ea09d90882db33a465e02cd27/68747470733a2f2f692e696d6775722e636f6d2f6a3841695046312e706e67" alt=""><figcaption></figcaption></figure>

Fix the logical error in local-6.rules file and make it work smoothly to create alerts.

What is the number of the detected packets?\
<mark style="color:yellow;">2</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/edfc0329a66b1a2413704fa631cc4b0e2d929bcf196ff2eeb57fb09d09da337e/68747470733a2f2f692e696d6775722e636f6d2f3130354b3935742e706e67" alt=""><figcaption></figcaption></figure>

Fix the logical error in **`local-7.rules`** file and make it work smoothly to create alerts.

**`What is the name of the required option:`**

<mark style="color:yellow;">msg</mark>
