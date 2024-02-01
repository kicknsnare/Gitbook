# Walkthrough

ANSWER 1,2

&#x20;<mark style="color:yellow;">Query:</mark> <mark style="color:yellow;"></mark><mark style="color:yellow;">`_path=="conn" | cut id.resp_p, service | sort | uniq -c | sort -r count`</mark>\


<figure><img src="https://camo.githubusercontent.com/3bbb20ce049ee011b40a0dc1f3ebb06ccfa5dfa225da14f5a9c13fe3714a0c40/68747470733a2f2f692e696d6775722e636f6d2f7870426c734d352e706e67" alt=""><figcaption></figcaption></figure>

How many connections used port 19999?

<mark style="color:green;">22</mark>



What is the name of the service used by port 6666?

<mark style="color:green;">irc</mark>



What is the amount of transferred total bytes to "101.201.172.235:8888"?

<mark style="color:green;">3,729</mark>

&#x20;ORIGINAL QUERY:

&#x20;<mark style="color:yellow;">`_path=="conn" | put total_bytes := orig_bytes + resp_bytes | sort -r total_bytes | cut uid, id, orig_bytes, resp_bytes, total_bytes`</mark>

<figure><img src="https://camo.githubusercontent.com/cd1ccfd85fd6e2d6dc2915f83da5bbcf23ce7dc6e8b6832b3e15b945427072ef/68747470733a2f2f692e696d6775722e636f6d2f6d474956356b6e2e706e67" alt=""><figcaption></figcaption></figure>



What is the detected MITRE tactic id?

<mark style="color:green;">TA0040</mark>\
Query:

<mark style="color:yellow;">`event_type=="alert"`</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/577606b3e6d802181aa07fc30b28dd2da032cb712736a2de30cf1326b1d63ed6/68747470733a2f2f692e696d6775722e636f6d2f4974486e64476f2e706e67" alt=""><figcaption></figcaption></figure>
