# Walkthrough

\
Investigate the files. What is the name of the detected GIF file?&#x20;

&#x20;

<figure><img src="https://camo.githubusercontent.com/22844dae3330ca677c219e9641d76b33ac67efb7ec97ac11ab4dae5dd0f2ca49/68747470733a2f2f692e696d6775722e636f6d2f463438455a486c2e706e67" alt=""><figcaption></figcaption></figure>



Investigate the conn logfile. What is the number of the identified city names?

&#x20;

<figure><img src="https://camo.githubusercontent.com/86ff461c7f52f0aea4b502fdbf4ad9fb398163fd20cdceb725b35d6ea9a33a3f/68747470733a2f2f692e696d6775722e636f6d2f496e6a664e53592e706e67" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/86fbcd6420d6e415e30dc3337fb523ca137bf409802b60f7d26e991321e83881/68747470733a2f2f692e696d6775722e636f6d2f416d524a796d342e706e67" alt=""><figcaption></figcaption></figure>

Investigate the Suricata alerts. What is the Signature id of the alert category "Potential Corporate Privacy Violation"?

```bash
event_type=="alert" | count() by alert.category, alert.signature_id | sort count
```

