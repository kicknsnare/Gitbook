# File and Disk Utilities

Sigcheck

"Sigcheck is a command-line utility that shows file version number, timestamp information, and digital signature details, including certificate chains. It also includes an option to check a file’s status on VirusTotal, a site that performs automated file scanning against over 40 antivirus engines, and an option to upload a file for scanning." (official definition)

\


<figure><img src="https://assets.tryhackme.com/additional/sysinternals/sigcheck1.png" alt=""><figcaption></figcaption></figure>

From the official Sigcheck [page](https://docs.microsoft.com/en-us/sysinternals/downloads/sigcheck), a use case is identified towards the bottom of the page.

If you completed the Core Windows Processes room you should be aware that the location of all the executables is `C:\Windows\System32`, except for Explorer.exe (which is `C:\Windows`).

Use Case: Check for unsigned files in C:\Windows\System32.

Command: `sigcheck -u -e C:\Windows\System32`

\


<figure><img src="https://assets.tryhackme.com/additional/sysinternals/sigcheck2.png" alt=""><figcaption></figcaption></figure>

Parameter usage:

* `-u` "If VirusTotal check is enabled, show files that are unknown by VirusTotal or have non-zero detection, otherwise show only unsigned files."
* `-e` "Scan executable images only (regardless of their extension)"

Note: If the results were different it would warrant an investigation into any listed executables. \


Streams

"The NTFS file system provides applications the ability to create alternate data streams of information. By default, all data is stored in a file's main unnamed data stream, but by using the syntax 'file:stream', you are able to read and write to alternates." (official definition)

Alternate Data Streams (ADS) is a file attribute specific to Windows NTFS (New Technology File System). Every file has at least one data stream ($DATA) and ADS allows files to contain more than one stream of data. Natively Window Explorer doesn't display ADS to the user. There are 3rd party executables that can be used to view this data, but Powershell gives you the ability to view ADS for files.

Malware writers have used ADS to hide data in an endpoint, but not all its uses are malicious. When you download a file from the Internet unto an endpoint, there are identifiers written to ADS to identify that it was downloaded from the Internet.

![Screenshot showing the execution of streams using the command prompt](https://assets.tryhackme.com/additional/sysinternals/streams1.png)

Example: A file downloaded from the Internet.

![Screenshot showing the execution of streams against SysinternalsSuite.zip](https://assets.tryhackme.com/additional/sysinternals/streams2.png)

Since the file has this identifier, additional security measures are added to its properties.

![Screenshot showing the file properties of SysinternalsSuite.zip](https://assets.tryhackme.com/additional/sysinternals/streams3.png)

You can read more on streams [here](https://docs.microsoft.com/en-us/sysinternals/downloads/streams).

SDelete

"SDelete is a command line utility that takes a number of options. In any given use, it allows you to delete one or more files and/or directories, or to cleanse the free space on a logical disk."

As per the official documentation page, SDelete (Secure Delete) implemented the DOD 5220.22-M (Department of Defense clearing and sanitizing protocol).

![Screenshot showing the implementation of the DoD 5220.22-M Wipe Method](https://assets.tryhackme.com/additional/sysinternals/sdelete.png)

Source: [https://www.lifewire.com/dod-5220-22-m-2625856](https://www.lifewire.com/dod-5220-22-m-2625856)

SDelete has been used by adversaries and is associated with MITRE techniques [T1485](https://attack.mitre.org/techniques/T1485/) (Data Destruction) and [T1070.004](https://attack.mitre.org/techniques/T1070/004/) (Indicator Removal on Host: File Deletion). It's MITRE ID [S0195](https://attack.mitre.org/software/S0195/).\


You can review this tool more in-depth by visiting its Sysinternals SDelete [page](https://docs.microsoft.com/en-us/sysinternals/downloads/sdelete).&#x20;

Other tools fall under the File and Disk Utilities category. I encourage you to explore these tools at your own leisure.

Link: [https://docs.microsoft.com/en-us/sysinternals/downloads/file-and-disk-utilities](https://docs.microsoft.com/en-us/sysinternals/downloads/file-and-disk-utilities)&#x20;
