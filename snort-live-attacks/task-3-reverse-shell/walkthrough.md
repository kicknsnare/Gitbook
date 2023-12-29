# Walkthrough

```bash
#Used Commands:

```

First of all, start Snort in sniffer mode and try to figure out the attack source, service and port.\
\


Then, write an IPS rule and run Snort in IPS mode to stop the brute-force attack. Once you stop the attack properly, you will have the flag on the desktop!

Here are a few points to remember:

* Create the rule and test it with "-A console" mode.&#x20;
* Use "-A full" mode and the default log path to stop the attack.
* Write the correct rule and run the Snort in IPS "-A full" mode.
* Block the traffic at least for a minute and then the flag file will appear on your desktop.

Stop the attack and get the flag (which will appear on your Desktop)\




What is the used protocol/port in the attack?\




Which tool is highly associated with this specific port number?
