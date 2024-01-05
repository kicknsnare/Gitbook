# Walkthrough

<pre class="language-bash"><code class="lang-bash">#commands
zeek -C -r sample.pcap 103.zeek | grep "New Connection" | wc -l
zeek -C -r sample.pcap 103.zeek | grep "New Connection" | awk '{print NR, $0}'
zeek -C -r ftp.pcap -s ftp-admin.sig 201.zeek
<strong>cat signatures.log | zeek-cut event_msg | grep -e "FTP*" | awk '{print NR, $0}'
</strong>cat signatures.log | zeek-cut sub_msg | grep "administrator" | awk '{print NR, $0}'
zeek -C -r ftp.pcap local
cat loaded_scripts.log | grep -e "/opt" | awk '{print NR, $0}'
zeek -C -r ftp-brute.pcap /opt/zeek/share/zeek/policy/protocols/ftp/detect-bruteforcing.zeek
</code></pre>

```bash
#awk note
{}: Encloses the set of commands to be executed by awk for each input line.
print NR, $0: print is an awk command that prints the specified values. 
NR represents the current record (line) number, 
and $0 represents the entire input line. 
```

\
Go to folder TASK-7/101.\
Investigate the sample.pcap file with 103.zeek script. Investigate the terminal output. What is the number of the detected new connections?

<mark style="color:green;">87</mark>

<figure><img src="https://camo.githubusercontent.com/ee556a839793ba97d0dd69f31634cd797bbce99af5bcc68d9574d6c797a0e2f0/68747470733a2f2f692e696d6775722e636f6d2f726d6a796c4c772e706e67" alt=""><figcaption></figcaption></figure>

Go to folder TASK-7/201.\
Investigate the ftp.pcap file with ftp-admin.sig signature and  201.zeek script. Investigate the signatures.log file. What is the number of signature hits?\
<mark style="color:green;">1401</mark>

<figure><img src="https://camo.githubusercontent.com/e799d42055d7dd9f14d2ffa00dce3ce527311af4c9a5a537f31dcb956fb866b6/68747470733a2f2f692e696d6775722e636f6d2f6b6b4d745848542e706e67" alt=""><figcaption></figcaption></figure>



Investigate the signatures.log file. What is the total number of "administrator" username detections?\
<mark style="color:green;">731</mark>

<figure><img src="https://camo.githubusercontent.com/a479aedab5105e9be54588e5ad000fab0cf1b0d8963dcc97a2082f36a6a9a4ae/68747470733a2f2f692e696d6775722e636f6d2f444f77773243722e706e67" alt=""><figcaption></figcaption></figure>

Investigate the ftp.pcap file with all local scripts, and investigate the loaded\_scripts.log file. What is the total number of loaded scripts?\
<mark style="color:green;">498</mark>



<figure><img src="https://camo.githubusercontent.com/5a6d968e3bc1b78efcfe5472ad491118f9eb6224ec3142476e10dde1277f561d/68747470733a2f2f692e696d6775722e636f6d2f386b37376354612e706e67" alt=""><figcaption></figcaption></figure>

Go to folder TASK-7/202.\
Investigate the ftp-brute.pcap file with "/opt/zeek/share/zeek/policy/protocols/ftp/detect-bruteforcing.zeek" script. Investigate the notice.log file. What is the total number of brute-force detections?

2



<figure><img src="https://camo.githubusercontent.com/2964c555da788ec1604957db256b163676397ae7f92954ad4ed70298a1563286/68747470733a2f2f692e696d6775722e636f6d2f617a35413976732e706e67" alt=""><figcaption></figcaption></figure>

\
