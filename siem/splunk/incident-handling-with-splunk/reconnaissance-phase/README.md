# Reconnaissance Phase

Reconnaissance Phase\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/fe02723595184431c7911543dc6c54d1.png" alt=""><figcaption></figcaption></figure>

Reconnaissance is an attempt to discover and collect information about a target. It could be knowledge about the system in use, the web application, employees or location, etc.

\


We will start our analysis by examining any reconnaissance attempt against the webserver `imreallynotbatman.com`. From an analyst perspective, where do we first need to look? If we look at the available log sources, we will find some log sources covering the network traffic, which means all the inbound communication towards our web server will be logged into the log source that contains the web traffic. Let's start by searching for the domain in the search head and see which log source includes the traces of our domain.

Search Query: `index=botsv1 imreallynotbatman.com`

Search Query explanation: We are going to look for the event logs in the index "botsv1" which contains the term `imreallynotbatman.com`

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/c320e7a1192dd94671fb5048e6a3cf3d.gif" alt=""><figcaption></figcaption></figure>

Here we have searched for the term `imreallynotbatman.com` in the index `botsv1`. In the sourcetype field, we saw that the following log sources contain the traces of this search term.

* Suricata
* stream:http
* fortigate\_utm
* iis

From the name of these log sources, it is clear what each log source may contain. Every analyst may have a different approach to investigating a scenario. Our first task is to identify the IP address attempting to perform reconnaissance activity on our web server. It would be obvious to look at the web traffic coming into the network. We can start looking into any of the logs mentioned above sources.

Let us begin looking at the log source stream:http, which contains the http traffic logs, and examine the `src_ip` field from the left panel. Src\_ip field contains the source IP address it finds in the logs.\


Search Query: `index=botsv1 imreallynotbatman.com sourcetype=stream:http`\


Search Query Explanation: This query will only look for the term  `imreallynotbatman.com`in the stream:http log source.\


\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/11b2317ec891d4b9b9a4c5bdaa594aa6.png" alt=""><figcaption></figcaption></figure>

Note: The important thing to note, if you don't find the field of interest, keep scrolling in the left panel. When you click on a field, it will contain all the values it finds in the logs.\
So far, we have found two IPs in the src\_ip field `40.80.148.42` and `23.22.63.114`. The first IP seems to contain a high percentage of the logs as compared to the other IP, which could be the answer. If you want to confirm further, click on each IP one by one, it will be added into the search query, and look at the logs, and you will find the answer.

To further confirm our suspicion about the IP address 40.80.148.42, click on the IP and examine the logs. We can look at the interesting fields like User-Agent, Post request, URIs, etc., to see what kind of traffic is coming from this particular IP.\


![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/6e4de3d85d3322f76b20c71ea020d0b4.gif)

We have narrowed down the results to only show the logs from the source IP 40.80.148.42, looked at the fields of interest and found the traces of the domain being probed.\


Validate the IP that is scanning\
\
So what do we need to do to validate the scanning attempt? Simple, dig further into the weblogs. Let us narrow down the result, look into the `suricata` logs, and see if any rule is triggered on this communication.

Search Query: `index=botsv1 imreallynotbatman.com src=40.80.148.42 sourcetype=suricata`\


Search Query Explanation: This query will show the logs from the suricata log source that are detected/generated from the source IP 40.80.248.42\


<div align="center">

<img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/ff5428b053d955ddc89da6ff9dc0f81e.gif" alt="">

</div>

\


We have narrowed our search on the src IP and looked at the source type `suricata` to see what Suricata triggered alerts. In the right panel, we could not find the field of our interest, so we clicked on more fields and searched for the fields that contained the signature alerts information, which is an important point to note.
