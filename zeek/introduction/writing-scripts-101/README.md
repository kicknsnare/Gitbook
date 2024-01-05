# Writing scripts 101

```bash
zeek -C -r <pcap_file> <script.zeek>
```

Scripts contain operators, types, attributes, declarations and statements, and directives. Let's look at a simple example event called "zeek\_init" and "zeek\_done". These events work once the Zeek process starts and stops. Note that these events don't have parameters, and some events will require parameters.

```bash
event zeek_init()
    {
     print ("Started Zeek!");
    }
event zeek_done()
    {
    print ("Stopped Zeek!");
    }

# zeek_init: Do actions once Zeek starts its process.
# zeek_done: Do activities once Zeek finishes its process.
# print: Prompt a message on the terminal.
```

Let's print the packet data to the terminal and see the raw data. In this script, we are requesting details of a connection and extracting them without any filtering or sorting of the data. To accomplish this, we are using the "new\_connection" event. This event is automatically generated for each new connection. This script provides bulk information on the terminal.

```bash
event new_connection(c: connection)
{
	print c;
}

```

To filter the event of interest, we will use the primary tag (in this case, it is c --comes from "c: connection"--), id value (id=), and field name. You should notice that the fields are the same as the fields in the log files.

```bash
event new_connection(c: connection)
{
	print ("###########################################################");
	print ("");
	print ("New Connection Found!");
	print ("");
	print fmt ("Source Host: %s # %s --->", c$id$orig_h, c$id$orig_p);
	print fmt ("Destination Host: resp: %s # %s <---", c$id$resp_h, c$id$resp_p);
	print ("");
}

# %s: Identifies string output for the source.
# c$id: Source reference field for the identifier.

```

a&#x20;

<figure><img src="https://camo.githubusercontent.com/2c4380737b61335f959e5acc5e8aea1ca450e39a0742c2c12f45e0a8f75d96c8/68747470733a2f2f692e696d6775722e636f6d2f545836364d55662e706e67" alt=""><figcaption></figcaption></figure>

```bash
#My notes %s i like a variable that you use and you have to give it
# a value after using c$id$orig_h (whatever)
```

