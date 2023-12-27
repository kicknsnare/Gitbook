# Walkthrough

## Configuration check

<mark style="color:green;">tag -c</mark>: identifies the configuration file and <mark style="color:green;">tag -T</mark>: testing

```bash
sudo snort -c /etc/snort/snort.conf -T 
```

Run the Snort instance and check the build number.

<mark style="color:yellow;">149</mark>

Test the current instance with "/etc/snort/snort.conf" file and check how many rules are loaded with the current build.

```bash
sudo snort -c /etc/snort/snort.conf -T
```

<mark style="color:yellow;">4151</mark>

Test the current instance with "/etc/snort/snortv2.conf" file and check how many rules are loaded with the current build.

```bash
sudo snort -c /etc/snort/snortv2.conf -T
```

<mark style="color:yellow;">1</mark>
