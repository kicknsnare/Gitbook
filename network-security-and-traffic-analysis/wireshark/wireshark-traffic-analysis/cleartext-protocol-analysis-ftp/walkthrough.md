# Walkthrough

\
Use the "Desktop/exercise-pcaps/ftp/ftp.pcap" file.\
How many incorrect login attempts are there?

&#x20;<mark style="color:green;">737</mark>

<figure><img src="https://camo.githubusercontent.com/9f7a997d7358c20252d834d75ac214df51ab1db01c3efcf11c092c5d05999fcd/68747470733a2f2f692e696d6775722e636f6d2f57366f483257682e706e67" alt=""><figcaption></figcaption></figure>

What is the size of the file accessed by the "ftp" account?

**`ftp.response.code== 230`**

&#x20;<mark style="color:green;">39424</mark>

<figure><img src="https://camo.githubusercontent.com/de5dc3388d77c5eca68447291dc39d60a6876bffd0d0bdf7079b341b7915a089/68747470733a2f2f692e696d6775722e636f6d2f556f476f4552522e706e67" alt=""><figcaption></figcaption></figure>

The adversary uploaded a document to the FTP server. What is the filename?

<mark style="color:green;">resume.doc</mark>

<figure><img src="https://camo.githubusercontent.com/77975f8ff7788cf5d7ed2b3ca9fc7f8cecd7fb61fe3b0514656d1fcaf14291dc/68747470733a2f2f692e696d6775722e636f6d2f584469576478552e706e67" alt=""><figcaption></figcaption></figure>

The adversary tried to assign special flags to change the executing permissions of the uploaded file. What is the command used by the adversary?

<mark style="color:green;">CHMOD 777</mark>

<figure><img src="https://camo.githubusercontent.com/53387879bfa6b20645ab3a6207c977bec8eded6d981d8b8d29ab7d6ffbf7c24c/68747470733a2f2f692e696d6775722e636f6d2f54534c533863672e706e6767" alt=""><figcaption></figcaption></figure>
