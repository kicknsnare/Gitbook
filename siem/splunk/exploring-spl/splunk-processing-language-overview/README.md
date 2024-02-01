# Splunk Processing Language Overview

Splunk Search Processing Language comprises of multiple functions, operators and commands that are used together to form a simple to complex search and get the desired results from the ingested logs. Main components of SPL are explained below:

﻿Search Field Operators\


Splunk field operators are the building blocks used to construct any search query. These field operators are used to filter, remove, and narrow down the search result based on the given criteria. Common field operators are Comparison operators, wildcards, and boolean operators.\


Comparison Operators

﻿These operators are used to compare the values against the fields. Some common comparisons operators are mentioned below:\


| <p>Field Name<br></p>               | <p>Operator<br></p> | <p>Example<br></p>                  | <p>Explanation<br></p>                                                                                                                                                        |
| ----------------------------------- | ------------------- | ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>Equal<br></p>                    | <p>=<br></p>        | UserName=Mark                       | <p>This operator is used to match values against the field. In this example, it will look for all the events, where the value of the field UserName is equal to Mark.<br></p> |
| <p>Not Equal to<br></p>             | <p>!=<br></p>       | UserName!=Mark                      | <p>This operator returns all the events where the UserName value does not match Mark.<br></p>                                                                                 |
| <p>Less than<br></p>                | <p>&#x3C;<br></p>   | Age < 10                            | <p>Showing all the events with the value of Age less than 10.<br></p>                                                                                                         |
| <p>Less than or Equal to<br></p>    | <p>&#x3C;=<br></p>  | Age <= 10                           | Showing all the events with the value of Age less than or equal to 10.                                                                                                        |
| <p>Greater than<br></p>             | <p>><br></p>        | <p>Outbound_traffic > 50 MB<br></p> | <p>This will return all the events where the Outbound traffic value is over 50 MB.<br></p>                                                                                    |
| <p>Greater Than or Equal to<br></p> | <p>>=<br></p>       | Outbound\_traffic >= 50 MB          | This will return all the events where the Outbound traffic value is greater or equal to 50 MB.                                                                                |

﻿﻿Lets use the comparison operator to display all the event logs from the index "windowslogs", where AccountName is not Equal to "System"

Search Query: `index=windowslogs AccountName !=SYSTEM`\


\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/681a126a98263612b87def7014583ffb.png" alt=""><figcaption></figcaption></figure>

Boolean Operators

Splunk supports the following Boolean operators, which can be very handy in searching/filtering and narrowing down results.\


| <p>Operator<br></p> | <p>Syntax<br></p>                           | <p>Explanation<br></p>                                                                         |
| ------------------- | ------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| <p>NOT<br></p>      | <p>field_A NOT value<br></p>                | <p>Ignore the events from the result where field_A contain the specified value.<br></p>        |
| <p>OR<br></p>       | <p>field_A=value1 OR field_A=value2<br></p> | <p>Return all the events in which field_A contains either value1 or value2.<br></p>            |
| <p>AND<br></p>      | field\_A=value1 AND field\_B=value2         | <p>Return all the events in which field_A contains value1 and field_B contains value2.<br></p> |

﻿To understand how boolean operator works in SPL, lets add the condition to show the events from the James account.

Search Query: `index=windowslogs AccountName !=SYSTEM AND AccountName=James`\


\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/42c8963dccbd05128f52665c38877f47.png" alt=""><figcaption></figcaption></figure>

\


Wild Card

Splunk supports wildcards to match the characters in the strings.\


| Wildcard symbol  | <p>Example   <br></p> | <p>Explanation         <br></p>                                                                     |
| ---------------- | --------------------- | --------------------------------------------------------------------------------------------------- |
| <p>*<br><br></p> | status=fail\*         | <p>It will return all the results with values like</p><p>status=failed</p><p>status=failure<br></p> |

In the events, there are multiple DestinationIPs reported. Let's use the wildcard only to show the DestinationIP starting from 172.\*

Search Query: `index=windowslogs DestinationIp=172.*`\


<div align="center">

<img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/5530cae0739755e6a682641f5057b1a5.png" alt="">

</div>
