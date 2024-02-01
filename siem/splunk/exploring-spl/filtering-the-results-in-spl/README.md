# Filtering the Results in SPL

Our network generates thousands of logs each minute, all ingesting into our SIEM solution. It becomes a daunting task to search for any anomaly without using filters. SPL allows us to use Filters to narrow down the result and only show the important events that we are interested in. We can add or remove certain data from the result using filters. The following commands are useful in applying filters to the search results.

Fields

| <p>Command<br></p>     | <p>fields                                                                                               <br></p>                                                                                                                   |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>Explanation<br></p> | <p>Fields command is used to add or remove mentioned fields from the search results. To remove the field, minus sign ( - ) is used before the fieldname and plus ( + ) is used before the fields which we want to display.<br></p> |
| <p>Syntax<br></p>      | \| fields \<field\_name1>  \<field\_name2>                                                                                                                                                                                         |
| <p>Example<br></p>     | <p>| <code>fields + HostName - EventID</code><br></p>                                                                                                                                                                              |

Let's use the fields command to only display host, User, and SourceIP fields using the following syntax.\


Search Query: `index=windowslogs | fields + host + User + SourceIp`\


\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/dd77983b5fccf5eacfa73aacbeb7a314.png" alt=""><figcaption></figcaption></figure>

Note: Click on the More field to display the fields if some fields are not visible.

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/30b2c651a041bd1c2db77b661dc8cc8e.png" alt=""><figcaption></figcaption></figure>

Search

| <p>Command<br></p>     | <p>search                                                                                               <br></p> |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------- |
| <p>Explanation<br></p> | This command is used to search for the raw text while using the chaining command `\|`                            |
| <p>Syntax<br></p>      | <p>| search  &#x3C;search_keyword><br></p>                                                                       |
| <p>Example<br></p>     | <p>| <code>search "Powershell"</code><br></p>                                                                    |

Use the search command to show all the events containing the term Powershell. This will return all the events that contain the term "Powershell".\


Search Query: `index=windowslogs | search Powershell`\


\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/02d2ece97e7f977e32b4c11fd86e41eb.png" alt=""><figcaption></figcaption></figure>

Dedup

| <p>Command<br></p>     | <p>dedup                                                                                        <br></p>                                                                                                             |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>Explanation<br></p> | Dedup is the command used to remove duplicate fields from the search results. We often get the results with various fields getting the same results. These commands remove the duplicates to show the unique values. |
| <p>Syntax<br></p>      | <p>| dedup &#x3C;fieldname><br></p>                                                                                                                                                                                  |
| <p>Example<br></p>     | <p>| <code>dedup EventID</code><br></p>                                                                                                                                                                              |

We can use the dedup command to show the list of unique EventIDs from a particular hostname.

Search Query: `index=windowslogs | table EventID User Image Hostname | dedup EventID`

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/47bb3fb904c84acdbe7cb89dda535ac1.png" alt=""><figcaption></figcaption></figure>

Rename

| <p>Command<br></p>     | <p>rename<br></p>                                                                                                                                                              |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p>Explanation<br></p> | It allows us to change the name of the field in the search results. It is useful in a scenario when the field name is generic or log, or it needs to be updated in the output. |
| <p>Syntax<br></p>      | <p>| rename  &#x3C;fieldname><br></p>                                                                                                                                          |
| <p>Example<br></p>     | \| `rename User as Employees`                                                                                                                                                  |

Let's rename the User field to Employees using the following search query.

Search Query:`index=windowslogs | fields + host + User + SourceIp | rename User as Employees`\


<div align="center">

<img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/61e56df15649aa12b4be7c91d8cc91ce.png" alt="">

</div>
