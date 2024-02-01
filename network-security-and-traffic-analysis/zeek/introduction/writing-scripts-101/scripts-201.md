# Scripts 201

{% embed url="https://docs.zeek.org/en/master/scripts/base/bif/event.bif.zeek.html" %}

## Running Local scripts

```bash
zeek -C -r ftp.pcap local 
#specific scripts 
zeek -C -r ftp.pcap /opt/zeek/share/zeek/policy/protocols/ftp/detect-bruteforcing.zeek 

```

## Zeek scripts and signatures together

Let's demonstrate this concept with an example. We will create a script that detects if our previously created "ftp-admin" rule has a hit.

```bash
signature ftp-admin {
     ip-proto == tcp
     ftp /.*USER.*dmin.*/
     event "FTP Admin Login Attempt!"
}

```

```markdown
event signature_match (state: signature_state, msg: string, data: string)
{
if (state$sig_id == "ftp-admin")
    {
    print ("Signature hit! --> #FTP-Admin ");
    }
}
```



## Running signatures and scripts

```bash
zeek -C -r ftp.pcap -s ftp-admin.sig 201.zeek 
```
