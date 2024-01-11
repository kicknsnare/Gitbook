# Walkthrough

\
Use the "Desktop/exercise-pcaps/bonus/Bonus-exercise.pcap" file.\
Select packet number 99. Create a rule for "IPFirewall (ipfw)". What is the rule for "denying source IPv4 address"?\
<mark style="color:green;">add deny ip from 10.121.70.151 to any in</mark>

<figure><img src="https://camo.githubusercontent.com/2bcaf727ceee9a83860236108ae867b437ab5da4d7094348af4cd5125563387e/68747470733a2f2f692e696d6775722e636f6d2f755466424f37372e706e67" alt=""><figcaption></figcaption></figure>

Select packet number 231. Create "IPFirewall" rules. What is the rule for "allowing destination MAC address"?

&#x20;<mark style="color:green;">add allow MAC 00:d0:59:aa:af:80 any in</mark>

<figure><img src="https://camo.githubusercontent.com/60f858fa744c4f66d1ff84823e0c26e112667be76fdc8c1a1bfb0a89f83ac481/68747470733a2f2f692e696d6775722e636f6d2f647a50715236442e706e67" alt=""><figcaption></figcaption></figure>
