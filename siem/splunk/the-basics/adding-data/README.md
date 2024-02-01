# Adding Data

Splunk can ingest any data. As per the Splunk documentation, when data is added to Splunk, the data is processed and transformed into a series of individual events.&#x20;

The data sources can be event logs, website logs, firewall logs, etc.

Data sources are grouped into categories. Below is a chart listing from the Splunk documentation detailing each data source category.

\


<figure><img src="https://assets.tryhackme.com/additional/splunk-overview/splunk-data-sources.png" alt=""><figcaption></figcaption></figure>

\


In this room, we're going to focus on VPN logs. When we click on the `Add Data` link (from the Splunk home screen), we're presented with the following screen.&#x20;

\


<figure><img src="https://assets.tryhackme.com/additional/splunk-overview/splunk-add-data.png" alt=""><figcaption></figcaption></figure>

We will use the Upload Option to upload the data from our local machine. Download the attached log file and upload it on Splunk.

As shown above, it has a total of 5 steps to successfully upload the data.

1. Select Source -> Where we select the Log source.
2. Select Source Type -> Select what type of logs are being ingested.
3. Input Settings ->Select the index where these logs will be dumped and hostName to be associated with the logs.\

4. Review -> Review all the gif\

5. Done -> Final step, where the data is uploaded successfully and ready to be analyzed.

<div align="center">

<img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/c36a6f1c70007602251f331aee914d5c.gif" alt="Data Ingestion Example">

</div>
