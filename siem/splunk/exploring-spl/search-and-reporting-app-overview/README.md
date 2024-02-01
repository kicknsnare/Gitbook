# Search & Reporting App Overview

Search & Reporting App is the default interface used to search and analyze the data on the Splunk Home page. It has various functionalities that assist analysts in improving the search experience.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/68395fd11ab6b3a4ebb5d4a4a77c8b36.png" alt=""><figcaption></figcaption></figure>

Some important functionalities present in the search App are explained below:

1\) Search Head:\
Search Head is where we use search processing language queries to look for the data.\


<div align="center">

<img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/b162472e5f02c1a9ec6b92ee052ff415.png" alt="">

</div>

\


2\) Time Duration:\
This tab option provides multiple options to select the time duration for the search. All-time will display the events in real-time. Similarly, the last 60 minutes will display all the events captured in the last hour.

<div align="center">

<img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/d759303fcea6ffaf5b48bea06abb383f.png" alt="">

</div>

\


3\) Search History:\
This tab saves the search queries that the user has run in the past along with the time when it was run. It lets the user click on the past searches and look at the result. The filter option is used to search for the particular query based on the term.\


<div align="center">

<img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/3b9087b12c5dd849dae2e61cdd7ba93a.png" alt="">

</div>

\


4\) Data Summary:\
This tab provides a summary of the data type, the data source, and the hosts that generated the events as shown below. This tab is very important feature used to get a brief idea about the network visibility.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/81459123900e070704fe4fdac9f9b33e.gif" alt=""><figcaption></figcaption></figure>

\


5\) Field Sidebar:\


The Field Sidebar can be found on the left panel of Splunk search. This sidebar has two sections showing selected fields and interesting fields. It also provides quick results, such as top values and raw values against each field.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/78cb1326f4351a7127062f2bc96273dc.png" alt=""><figcaption></figcaption></figure>

\


Some important points to understand about the sidebar are explained below:

| 1- Selected Fields          | Splunk extracts the default fields like source, sourcetype, and host, which appear in each event, and places them under the selected fields column. We can select other fields that seem essential and add them to the list. |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2- Interesting Fields       | Pulls all the interesting fields it finds and displays them in the left panel to further explore.                                                                                                                            |
| 3- Alpha-numeric fields 'α' | This alpha symbol shows that the field contains text values.                                                                                                                                                                 |
| 4- Numeric fields '#'       | This symbol shows that this field contains numerical values.                                                                                                                                                                 |
| 5- Count                    | The number against each field shows the number of events captured in that timeframe.                                                                                                                                         |
