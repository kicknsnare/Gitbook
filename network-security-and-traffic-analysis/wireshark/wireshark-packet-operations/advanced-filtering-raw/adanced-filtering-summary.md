# Adanced Filtering summary



```bash
#Contain Filter
http.server contains "Apache" <- Keyword
#Matches Filter (it is case insensitive)
http.host matches "\.(php|html)" <- regular expression 
#In filter
tcp.port in {80 443 8080} <- scope/range
#Upper and lower Filter
upper(http.server) contains "APACHE" #Find all "APACHE" servers.
lower(http.server) contains "apache" #Find all "apache" servers.
#String 
string(frame.number) matches "[13579]$" #Find all frames with odd numbers
even == "[02468]$"
```
