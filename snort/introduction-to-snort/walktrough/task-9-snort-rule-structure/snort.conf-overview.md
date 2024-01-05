# snort.conf overview

Let's start with overviewing the main configuration file (snort.conf) `sudo gedit /etc/snort/snort.conf`

Navigate to the "Step #1: Set the network variables." section.

This section manages the scope of the detection and rule paths.\


| TAG NAME                     | INFO                                                                                           | EXAMPLE                               |
| ---------------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------- |
| <p>HOME_NET<br></p>          | <p>That is where we are protecting.<br></p>                                                    | <p> 'any' OR '192.168.1.1/24'<br></p> |
| <p>EXTERNAL_NET <br></p>     | <p>This field is the external network, so we need to keep it as 'any' or '!$HOME_NET'.<br></p> | <p>'any' OR '!$HOME_NET'<br></p>      |
| <p>RULE_PATH<br></p>         | <p>Hardcoded rule path.<br></p>                                                                | <p>/etc/snort/rules<br></p>           |
| <p>SO_RULE_PATH<br></p>      | <p><em>These rules come with registered and subscriber rules.</em><br></p>                     | <p>$RULE_PATH/so_rules<br></p>        |
| <p>PREPROC_RULE_PATH<br></p> | <p><em>These rules come with registered and subscriber rules.</em><br></p>                     | <p>$RULE_PATH/plugin_rules<br></p>    |

\
Navigate to the "Step #2: Configure the decoder." section.\


In this section, you manage the IPS mode of snort. The single-node installation model IPS model works best with "afpacket" mode. You can enable this mode and run Snort in IPS.

| TAG NAME           | INFO                        | EXAMPLE         |
| ------------------ | --------------------------- | --------------- |
| #config daq:       | IPS mode selection.         | afpacket        |
| #config daq\_mode: | Activating the inline mode  | inline          |
| #config logdir:    | Hardcoded default log path. | /var/logs/snort |

Data Acquisition Modules (DAQ) are specific libraries used for packet I/O, bringing flexibility to process packets. It is possible to select DAQ type and mode for different purposes.

There are six DAQ modules available in Snort;

* Pcap: Default mode, known as Sniffer mode.
* Afpacket: Inline mode, known as IPS mode.
* Ipq: Inline mode on Linux by using Netfilter. It replaces the snort\_inline patch. &#x20;
* Nfq: Inline mode on Linux.
* Ipfw: Inline on OpenBSD and FreeBSD by using divert sockets, with the pf and ipfw firewalls.\

* Dump: Testing mode of inline and normalisation.

The most popular modes are the default (pcap) and inline/IPS (Afpacket).

Navigate to the "Step #6: Configure output plugins" section.

This section manages the outputs of the IDS/IPS actions, such as logging and alerting format details. The default action prompts everything in the console application, so configuring this part will help you use the Snort more efficiently.&#x20;

Navigate to the "Step #7: Customise your ruleset" section.\


| TAG NAME                         | INFO                                                | EXAMPLE                                   |
| -------------------------------- | --------------------------------------------------- | ----------------------------------------- |
| <p># site specific rules<br></p> | Hardcoded local and user-generated rules path.      | <p>include $RULE_PATH/local.rules<br></p> |
| <p>#include $RULE_PATH/<br></p>  | <p>Hardcoded default/downloaded rules path.<br></p> | include $RULE\_PATH/rulename              |

Note that "#" is commenting operator. You should uncomment a line to activate it.
