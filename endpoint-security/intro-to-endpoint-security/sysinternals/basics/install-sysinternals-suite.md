# Install Sysinternals Suite

If you wish to download the Sysinternals Suite, you can download the zip file from [here](https://docs.microsoft.com/en-us/sysinternals/downloads/sysinternals-suite).

The suite has a select number of Sysinternal tools. See below for a rundown of the tools included in the suite.

\


<figure><img src="https://assets.tryhackme.com/additional/sysinternals/sysint-suite.png" alt=""><figcaption></figcaption></figure>

After you download the zip file, you need to extract the files. After the files are extracted, the extra step, which is by choice, is to add the folder path to the environment variables. By doing so, you can launch the tools via the command line without navigating to the directory the tools reside in.&#x20;

Environment Variables can be edited from System Properties.

The System Properties can be launched via the command line by running `sysdm.cpl`. Click on the `Advanced` tab.&#x20;

\


<figure><img src="https://assets.tryhackme.com/additional/sysinternals/env-variables.png" alt=""><figcaption></figcaption></figure>

Select `Path` under `System Variables` and select Edit... then OK.

\


<figure><img src="https://assets.tryhackme.com/additional/sysinternals/env-variables2.png" alt=""><figcaption></figcaption></figure>

In the next screen select `New` and enter the folder path where the Sysinternals Suite was extracted to. Press OK to confirm the changes.

\


<figure><img src="https://assets.tryhackme.com/additional/sysinternals/env-variables3.png" alt=""><figcaption></figcaption></figure>

Open a new command prompt (elevated) to confirm that the Sysinternals Suite can be executed from any location.

\


<figure><img src="https://assets.tryhackme.com/additional/sysinternals/env-variables4.png" alt=""><figcaption></figcaption></figure>

A local copy of the Sysinternals Suite is located in `C:\Tools\Sysint`.&#x20;

Alternatively, a PowerShell module can download and install all of the Sysinternals tools.&#x20;

* PowerShell command: `Download-SysInternalsTools C:\Tools\Sysint`
