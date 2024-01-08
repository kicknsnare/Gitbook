---
description: simple theory of each collection method
---

# PCAP collections methods

Some things to think about before going headfirst into attempting to collect and monitor live packet captures.

* Begin by starting with a sample capture to ensure that everything is correctly set up and you are successfully capturing traffic.
* Ensure that you have enough compute power to handle the number of packets based on the size of the network, this will obviously vary network by network.
* Ensure enough disk space to store all of the packet captures.

Once you meet all these criteria and have a collection method picked out you can begin to actively monitor and collect packets on a network.

\


## Network Taps

Physically implant a hardware or a network tap to the cable to start sniffing the packets



## MAC Floods

MAC Flooding is intended to stress the switch and fill the CAM table. Once the CAM table is filled the switch will no longer accept new MAC addresses and so in order to keep the network alive, the switch will send out packets to all ports of the switch.\


## ARP Poisoning

By ARP Poisoning you can redirect the traffic from the host(s) to the machine you're monitoring from.
