# Walkthrough

Investigate the traffic with the default configuration file.\


`sudo snort -c /etc/snort/snort.conf -A full -l .`

Execute the traffic generator script and choose "TASK-7 Exercise". Wait until the traffic stops, then stop the Snort instance. Now analyse the output summary and answer the question.

`sudo ./traffic-generator.sh`

What is the number of the detected HTTP GET methods?

<mark style="color:yellow;">2</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/e150f01cfc377bcd632160013e8fb5f2010c8521ed1d666e4f2dc1bc7fa43ddf/68747470733a2f2f692e696d6775722e636f6d2f316367546139342e6a7067" alt="" width="375"><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/63a6f6985fac5d4301803799ab4d4cb9332ba0a031a1cdfe5e249064a00fefb0/68747470733a2f2f692e696d6775722e636f6d2f476a77316c576a2e6a7067" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/ab9ad41cf9289fabdce54e58875b65b785d1400bd105524d5f5ae6e1cbb61ee1/68747470733a2f2f692e696d6775722e636f6d2f5879793969497a2e6a7067" alt=""><figcaption></figcaption></figure>
