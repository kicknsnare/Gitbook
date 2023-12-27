# Walkthrough

Investigate the traffic with the default configuration file.\


`sudo snort -c /etc/snort/snort.conf -A full -l .`

Execute the traffic generator script and choose "TASK-7 Exercise". Wait until the traffic stops, then stop the Snort instance. Now analyse the output summary and answer the question.

`sudo ./traffic-generator.sh`

What is the number of the detected HTTP GET methods?

<mark style="color:yellow;">2</mark>
