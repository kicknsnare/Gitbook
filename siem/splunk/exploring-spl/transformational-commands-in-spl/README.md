# Transformational Commands in SPL

Transformational commands are those commands that change the result into a data structure from the field-value pairs. These commands simply transform specific values for each event into numerical values which can easily be utilized for statistical purposes or turn the results into visualizations. Searches that use these transforming commands are called transforming searches. Some of the most used transforming commands are explained below.

General Transformational Commands\


Top\


| <p>Command<br></p>     | <p>top<br></p>                                                            |
| ---------------------- | ------------------------------------------------------------------------- |
| <p>Explanation<br></p> | This command returns frequent values for the top 10 events.               |
| <p>Syntax<br></p>      | <p>| top  &#x3C;field_name></p><p>| top limit=6 &#x3C;field_name><br></p> |
| <p>Example<br></p>     | `top limit=3 EventID`                                                     |

The following command will display the top 7 Image ( representing Processes) captured.

Search Query: `index=windowslogs | top limit=7 Image`

\
\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/ffef6c0a6ce0159e6d970de2c32921a3.png" alt=""><figcaption></figcaption></figure>

Rare\


| <p>Command<br></p>     | <p>rare<br></p>                                                                                             |
| ---------------------- | ----------------------------------------------------------------------------------------------------------- |
| <p>Explanation<br></p> | This command does the opposite of top command as it returns the least frequent values or bottom 10 results. |
| <p>Syntax<br></p>      | <p>| rare &#x3C;field_name></p><p>| rare limit=6 &#x3C;field_name><br></p>                                  |
| <p>Example<br></p>     | `rare limit=3 EventID`                                                                                      |

The following command will display the rare 7 Image (Processes) captured.

Search Query: `index=windowslogs | rare limit=7 Image`\


\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/8123e0932c169514d9842fbba8f5898c.png" alt=""><figcaption></figcaption></figure>

Highlight

| <p>Command<br></p>     | <p>highlight<br></p>                                                                |
| ---------------------- | ----------------------------------------------------------------------------------- |
| <p>Explanation<br></p> | The highlight command shows the results in raw events mode with fields highlighted. |
| <p>Syntax<br></p>      | highlight      \<field\_name1>      \<field\_name2>                                 |
| <p>Example<br></p>     | `highlight User, host, EventID, Image`                                              |

The following command will highlight the three mentioned fields in the raw logs\


Search Query: `index=windowslogs | highlight User, host, EventID, Image`

\


\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/61ad47b204639fa0f75b278bec21abac.gif" alt=""><figcaption></figcaption></figure>

\


STATS Commands

SPL supports various stats commands that help in calculating statistics on the values. Some common stat commands are:

| <p>Command<br></p> | <p>Explanation<br></p>                                            | <p>Syntax<br></p>                  | <p>Example<br></p>                 |
| ------------------ | ----------------------------------------------------------------- | ---------------------------------- | ---------------------------------- |
| <p>Average<br></p> | This command is used to calculate the average of the given field. | stats avg(field\_name)             | stats avg(product\_price)          |
| <p>Max<br></p>     | It will return the maximum value from the specific field.         | stats max(field\_name)             | stats max(user\_age)               |
| <p>Min<br></p>     | It will return the minimum value from the specific field.         | stats min(field\_name)             | stats min(product\_price)          |
| <p>Sum<br></p>     | It will return the sum of the fields in a specific value.         | stats sum(field\_name)             | <p>stats sum(product_cost)<br></p> |
| <p>Count<br></p>   | The count command returns the number of data occurrences.         | stats count(function) AS new\_NAME | stats count(source\_IP)            |

Splunk Chart Commands\


These are very important types of transforming commands that are used to present the data in table or visualization form. Most of the chart commands utilize various stat commands.

Chart

| <p>Command<br></p>     | <p>chart<br></p>                                                                          |
| ---------------------- | ----------------------------------------------------------------------------------------- |
| <p>Explanation<br></p> | <p>The chart command is used to transform the data into tables or visualizations.<br></p> |
| <p>Syntax<br></p>      | <p>| chart &#x3C;function><br></p>                                                        |
| <p>Example<br></p>     | \| `chart count by User`                                                                  |

Search Query: `index=windowslogs | chart count by User`

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/a954b0a1d37542650df294461d756c61.gif" alt=""><figcaption></figcaption></figure>

Timechart

| <p>Command<br></p>     | <p>timechart<br></p>                                                                                                                         |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>Explanation<br></p> | The timechart command returns the time series chart covering the field following the function mentioned. Often combined with STATS commands. |
| <p>Syntax<br></p>      | \| timechart function  \<field\_name>                                                                                                        |
| <p>Example<br></p>     | \| `timechart count by Image`                                                                                                                |

The following query will display the Image chart based on the time.\


Search Query: `index=windowslogs | timechart count by Image`

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/bc7f90e4f40be4c047d250d5e3ee44c8.gif" alt=""><figcaption></figcaption></figure>
