# Discovery Tab

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/9635453d465f7625f5dfda21966aa6a6.png" alt=""><figcaption></figcaption></figure>

Some key information available in a dashboard interface are

1. Logs (document): Each log here is also known as a single document containing information about the event. It shows the fields and values found in that document.
2. Fields pane: Left panel of the interface shows the list of the fields parsed from the logs. We can click on any field to add the field to the filter or remove it from the search.
3. Index Pattern: Let the user select the index pattern from the available list.
4. Search bar: A place where the user adds search queries / applies filters to narrow down the results.
5. Time Filter: We can narrow down results based on the time duration. This tab has many options to select from to filter/limit the logs.
6. Time Interval: This chart shows the event counts over time.
7. TOP Bar: This bar contains various options to save the search, open the saved searches, share or save the search, etc.



## Quick Select

The <mark style="color:blue;">**`Refresh, Every`**</mark> option at the end will allow us to choose the time to refresh the logs continuously.

## Index Pattern

**Index pattern** tells Kibana which elasticsearch data we want to explore. Each Index pattern corresponds to certain defined properties of the fields.

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/7a417aad777ee8afa398d98532f68478.png" alt=""><figcaption></figcaption></figure>

## Left Panel

Click on any field, and it will show the top 5 values and the percentage of the occurrence.

We can use these values to apply filters to them. Clicking on the + button will add a filter to show the logs containing this value, and the - button will apply the filter on this value to show the results that do not have this value.

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/aa7c29f3d971ce34a6f69c0dd9b1be86.png" alt=""><figcaption></figcaption></figure>

## Add filter option

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/f8f4399d7fbfc14c0a6659da697af1db.gif" alt=""><figcaption></figcaption></figure>



## Create Table

By default, the documents are shown in raw form. We can click on any document and select important fields to create a table showing only those fields. This method reduces the noise and makes it more presentable and meaningful.

![Shows steps to create table by selecting fields and remove noise](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/ed538dabafffd64020b51f88fabce8f9.gif)
