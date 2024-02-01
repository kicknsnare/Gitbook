# Walkthrough

## Configuration check

<mark style="color:green;">tag -c</mark>: identifies the configuration file and <mark style="color:green;">tag -T</mark>: testing

```bash
sudo snort -c /etc/snort/snort.conf -T 
```

&#x20;

<figure><img src="https://camo.githubusercontent.com/be6a67fae45aed2178e3844054bf327611e7ff2b4d9e599636e90f7d51d2eccc/68747470733a2f2f692e696d6775722e636f6d2f584c57514c79542e6a7067" alt=""><figcaption></figcaption></figure>

Run the Snort instance and check the build number.

<mark style="color:yellow;">149</mark>

&#x20;

<figure><img src="https://camo.githubusercontent.com/bc8af61f134ee96ad15ee9adfdef6757f4280ecd1986b63f6cfbf7d9c4c57cc5/68747470733a2f2f692e696d6775722e636f6d2f363763506d726e2e6a7067" alt=""><figcaption></figcaption></figure>

Test the current instance with "/etc/snort/snort.conf" file and check how many rules are loaded with the current build.

```bash
sudo snort -c /etc/snort/snort.conf -T
```

&#x20;

<figure><img src="https://camo.githubusercontent.com/5f9b7376e1ed0e0711f87ea65e64cfd490ae1307317a1238c3843e3c78e19ffe/68747470733a2f2f692e696d6775722e636f6d2f42396c73504b632e6a7067" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="https://camo.githubusercontent.com/a472f73659b4d9eadd23812c47c892b93cc1bbf491fffecd031c6cbca6bf796b/68747470733a2f2f692e696d6775722e636f6d2f637533694446392e6a7067" alt=""><figcaption></figcaption></figure>

<mark style="color:yellow;">4151</mark>

Test the current instance with "/etc/snort/snortv2.conf" file and check how many rules are loaded with the current build.

```bash
sudo snort -c /etc/snort/snortv2.conf -T
```

&#x20;

<figure><img src="https://camo.githubusercontent.com/e33b2823a8c2467cce86ea2afe044874f6f72b998d7eab41ec468db39e8fe730/68747470733a2f2f692e696d6775722e636f6d2f4b4a6b46506c392e6a7067" alt=""><figcaption></figcaption></figure>

<mark style="color:yellow;">1</mark>
