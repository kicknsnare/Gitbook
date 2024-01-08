# Walkthrough

What is the number of IP packets?

&#x20;

<figure><img src="https://camo.githubusercontent.com/af197ed9e41365d366e8f8cc4546b6bb5350833350188eea14ef80c05c6dae19/68747470733a2f2f692e696d6775722e636f6d2f4c347a5669715a2e706e67" alt=""><figcaption></figcaption></figure>

What is the number of packets with a "TTL value less than 10"?\
<mark style="color:yellow;">**`ip.ttl<10`**</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/ad99d07075cf46691eb1da1f13e17a7961ab3ae986b2f57d082ed7c36b3ecb9f/68747470733a2f2f692e696d6775722e636f6d2f6f4168325168622e706e67" alt=""><figcaption></figcaption></figure>

What is the number of packets which uses "TCP port 4444"?\
&#x20;

<figure><img src="https://camo.githubusercontent.com/70566ea3ccbe2fbcf8bf25316be553d986578b6d6a2a67f0a6c5e4e94b96e9cb/68747470733a2f2f692e696d6775722e636f6d2f366c4b633841472e706e67" alt=""><figcaption></figcaption></figure>



What is the number of "HTTP GET" requests sent to port "80"?\
&#x20;http.request.method=="GET" and tcp.dstport == 80

&#x20;

<figure><img src="https://camo.githubusercontent.com/991106ad60b858451989f30881cd93e78a51041296d0daf0fd07c822afe4a993/68747470733a2f2f692e696d6775722e636f6d2f4d346d494374792e706e67" alt=""><figcaption></figcaption></figure>

What is the number of "type A DNS Queries"?

dns.a

&#x20;

<figure><img src="https://camo.githubusercontent.com/ba5e8af047a874de217fd929eb822ecae0431536d89961d20561a34a58e809f8/68747470733a2f2f692e696d6775722e636f6d2f746570555857752e706e67" alt=""><figcaption></figcaption></figure>
