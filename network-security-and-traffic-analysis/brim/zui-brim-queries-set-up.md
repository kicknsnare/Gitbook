# 🥑 Zui (BRIM) queries set up

<pre class="language-bash"><code class="lang-bash">#Activity Overview
count() by _path | sort -r
#Unique DNS Queries
_path=="dns" | count() by query | sort -r
#Windows Networking Activity
_path matches smb* OR _path=="dce_rpc"
#HTTP Requests
_path=="http" | cut id.orig_h, id.resp_h, id.resp_p, method, host, uri | uniq
#Unique Networking Connections
_path=="conn" | cut id.orig_h, id.resp_p, id.resp_h | sort | uniq
#Connection Received Data
_path=="conn" | put total_bytes := orig_bytes + resp_bytes | sort -r total_bytes | cut uid, id, orig_bytes, resp_bytes, total_bytes
#File Activity
filename!=null | cut _path, tx_hosts, rx_hosts, conn_uids, mime_type, filename, md5, sha1
#Http Post Requests
method=="POST" | cut ts, uid, id, method, uri, status_code
#Show IP Subnets
_path=="conn" | put classnet := network_of(id.resp_h) | cut classnet | count() by classnet | sort -r
#Suricata Alerts by Category
event_type=="alert" | count() by alert.severity,alert.category | sort count
#Suricata Alerts by Source and Destination
<strong>event_type=="alert" | alerts := union(alert.category) by src_ip, dest_ip
</strong>#Suricata Alerts by Subnet
event_type=="alert" | alerts := union(alert.category) by network_of(dest_ip)
</code></pre>
