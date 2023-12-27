# Walkthrough

\
Investigate the traffic with the default configuration file with ASCII mode.\


`sudo snort -dev -K ASCII -l .`

Execute the traffic generator script and choose "TASK-6 Exercise". Wait until the traffic ends, then stop the Snort instance. Now analyse the output summary and answer the question.

`sudo ./traffic-generator.sh`

Now, you should have the logs in the current directory. Navigate to folder "145.254.160.237". What is the source port used to connect port 53?&#x20;

<mark style="color:yellow;">3009</mark>

Use snort.log.1640048004 \


Read the snort.log file with Snort; what is the IP ID of the 10th packet?

`snort -r snort.log.1640048004 -n 10`

<mark style="color:yellow;">49313</mark>

Read the "snort.log.1640048004" file with Snort; what is the referer of the 4th packet?\


[ ](http://www.ethereal.com/development.html)[<mark style="color:yellow;">http://www.ethereal.com/development.html</mark>](http://www.ethereal.com/development.html)

Read the "snort.log.1640048004" file with Snort; what is the Ack number of the 8th packet?\


&#x20;<mark style="color:yellow;">0x38AFFFF3</mark>

Read the "snort.log.1640048004" file with Snort; what is the number of the "TCP port 80" packets?

<mark style="color:yellow;">41</mark>
