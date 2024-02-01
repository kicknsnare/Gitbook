# Advanced Filtering RAW

## Filter Contains

| <p>Filter<br></p> | <p>contains<br></p>                                                                                                                                     |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Type              | <p>Comparison Operator<br></p>                                                                                                                          |
| Description       | <p>Search a value inside packets. It is case-sensitive and provides similar functionality to the "Find" option by focusing on a specific field.<br></p> |
| Example           | <p>Find all "Apache" servers.<br></p>                                                                                                                   |
| Workflow          | <p>List all HTTP packets where packets' "server" field contains the "Apache" keyword.<br></p>                                                           |
| Usage             | <p><code>http.server contains "Apache"</code><br></p>                                                                                                   |

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/fb733f3af660c22a26d44e4087dc38a3.png" alt=""><figcaption></figcaption></figure>





## Filter matches

| <p>Filter<br></p> | <p>matches<br></p>                                                                                                       |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Type              | <p>Comparison Operator<br></p>                                                                                           |
| Description       | <p>Search a pattern of a regular expression. It is case insensitive, and complex queries have a margin of error.<br></p> |
| Example           | <p>Find all .php and .html pages.<br></p>                                                                                |
| Workflow          | <p>List all HTTP packets where packets' "host" fields match keywords ".php" or ".html".<br></p>                          |
| Usage             | <p><code>http.host matches "\.(php|html)"</code><br></p>                                                                 |

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/c7c03c7306f9965b97423f8431a944cb.png" alt=""><figcaption></figcaption></figure>



## Filter in

| <p>Filter<br></p> | <p>in<br></p>                                                                             |
| ----------------- | ----------------------------------------------------------------------------------------- |
| Type              | <p> Set Membership<br></p>                                                                |
| Description       | <p>Search a value or field inside of a specific scope/range.<br></p>                      |
| Example           | <p>Find all packets that use ports 80, 443 or 8080.<br></p>                               |
| Workflow          | <p>List all TCP packets where packets' "port" fields have values 80, 443 or 8080.<br></p> |
| Usage             | <p><code>tcp.port in {80 443 8080}</code><br></p>                                         |

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/db1cac52cf9ff629c21d104834cb689e.png" alt=""><figcaption></figcaption></figure>



## Filter upper

| <p>Filter<br></p> | <p>upper<br></p>                                                                                                      |
| ----------------- | --------------------------------------------------------------------------------------------------------------------- |
| Type              | <p>Function<br></p>                                                                                                   |
| Description       | <p>Convert a string value to uppercase.<br></p>                                                                       |
| Example           | <p>Find all "APACHE" servers.<br></p>                                                                                 |
| Workflow          | <p>Convert all HTTP packets' "server" fields to uppercase and list packets that contain the "APACHE" keyword.<br></p> |
| Usage             | <p><code>upper(http.server) contains "APACHE"</code><br></p>                                                          |

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/289b8e6c53ab1adfd894874b7053de75.png" alt=""><figcaption></figcaption></figure>



## Filter Lower

| <p>Filter<br></p> | <p>lower<br></p>                                                                                                           |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Type              | <p>Function<br></p>                                                                                                        |
| Description       | <p>Convert a string value to lowercase.<br></p>                                                                            |
| Example           | <p>Find all "apache" servers.<br></p>                                                                                      |
| Workflow          | <p>Convert all HTTP packets' "server" fields info to lowercase and list packets that contain the "apache" keyword.<br></p> |
| Usage             | <p><code>lower(http.server) contains "apache"</code><br></p>                                                               |

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/6cb5da0c3d4b10a3f29f15a193b9ab92.png" alt=""><figcaption></figcaption></figure>

## Filter String

| <p>Filter<br></p> | <p>string<br></p>                                                                                   |
| ----------------- | --------------------------------------------------------------------------------------------------- |
| Type              | <p>Function<br></p>                                                                                 |
| Description       | <p>Convert a non-string value to a string.<br></p>                                                  |
| Example           | <p>Find all frames with odd numbers.<br></p>                                                        |
| Workflow          | <p>Convert all "frame number" fields to string values, and list frames end with odd values.<br></p> |
| Usage             | <p><code>string(frame.number) matches "[13579]$"</code><br></p>                                     |

## Profiles

You can create multiple profiles for different investigation cases and use them accordingly. You can use the "Edit --> Configuration Profiles" menu or the "lower right bottom of the status bar --> Profile" section to create, modify and change the profile configuration.

![Wireshark - profiles](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/9254b0bb582c55723327550a68c9a11e.png)
