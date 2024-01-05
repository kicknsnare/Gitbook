# Useful Queries

\_path=="conn" id.resp\_p==\<port> | count() by id.resp\_p

\_path=="conn" id.resp\_p==\<port> | cut service | uniq

Filter IP and Port :&#x20;

* \<IP> | \<PORT>

\_path=="conn" | put total\_bytes := orig\_bytes + resp\_bytes | \<IP> | \<PORT>| cut uid, id, orig\_bytes, resp\_bytes, total\_bytes
