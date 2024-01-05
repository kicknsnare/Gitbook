# Creating queries

_path=='LOG\_TO\_FILTER_' | cut \<zeek\_field> | \<commands>

Example&#x20;

\_path=='conn' | cut geo.resp.city | sort | uniq -c
