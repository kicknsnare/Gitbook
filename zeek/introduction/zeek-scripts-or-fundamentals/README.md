# Zeek Scripts | Fundamentals

```bash
zeek -C -r <pcap> <script.zeek>
```

## Zeek repo

{% embed url="https://docs.zeek.org/en/master/script-reference/scripts.html" %}

## Zeek's Scripts Path

| <p>Zeek has base scripts installed by default, and these are not intended to be modified.<br></p>                                                                                                         | <p>These scripts are located in<br> "/opt/zeek/share/zeek/base".<br></p>                    |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| User-generated or modified scripts should be located in a specific path.                                                                                                                                  | <p>These scripts are located in<br>"/opt/zeek/share/zeek/site".<br></p>                     |
| Policy scripts are located in a specific path.                                                                                                                                                            | <p>These scripts are located in<br> "/opt/zeek/share/zeek/policy".<br></p>                  |
| Like Snort, to automatically load/use a script in live sniffing mode, you must identify the script in the Zeek configuration file. You can also use a script for a single run, just like the signatures.  | <p>The configuration file is located in<br> "/opt/zeek/share/zeek/site/local.zeek".<br></p> |



* Zeek scripts use the ".zeek" extension.\

* Do not modify anything under the "zeek/base" directory. User-generated and modified scripts should be in the "zeek/site" directory.
* You can call scripts in live monitoring mode by loading them with the command `load @/script/path` or `load @script-name` in local.zeek file. \

* Zeek is event-oriented, not packet-oriented! We need to use/write scripts to handle the event of interest.

\
