# Sysinternals Live

Simply enter a tool's Sysinternals Live path into Windows Explorer or a command prompt as <mark style="color:blue;">**`live.sysinternals.com/`**</mark> or <mark style="color:blue;">**`\live.sysinternals.com\tools<toolname>`**</mark>



Let's take a look at how we can do this.

Based on the instructions, to launch Process Monitor from the web the syntax is `\\live.sysinternals.com\tools\procmon.exe`.

And it fails.

![Screenshot showing the error: cannot find the path specified](https://assets.tryhackme.com/additional/sysinternals/sysint-live-fail.png)

To resolve this issue the WebDAV client must be installed and running on the machine. The WebDAV protocol is what allows a local machine to access a remote machine running a WebDAV share and perform actions in it.

On a Windows 10 client, the WebDAV client is installed but the client is most likely not running. If you try to run a Sysinternals tool it will fail with a message "The network path was not found."

![Screenshot showing the steps to start the webclient service and fix the error: the network path was not found](https://assets.tryhackme.com/additional/sysinternals/win10-webclient1b.png)\


The service needs to be started before attempting to call any Sysinternals tool in this fashion.

![Screenshot showing the command prompt executing get-service webclient](https://assets.tryhackme.com/additional/sysinternals/win10-webclient2.png)\


Verify it's running before proceeding.

![Screenshot showing the command prompt executing get-service webclient and confirming that it is Running](https://assets.tryhackme.com/additional/sysinternals/win10-webclient3.png)\


Also, Network Discovery needs to be enabled as well. This setting can be enabled in the Network and Sharing Center.

There are a few ways to open the Network and Sharing Center. Here is a neat command line to launch it.

![Screenshot showing the command prompt used to open the Network and Sharing Center](https://assets.tryhackme.com/additional/sysinternals/network-and-sharing.png)\


Click on `Change advanced sharing settings` and select `Turn on network discovery` for your current network profile.

The attached VM is a Windows Server 2019 edition. The WebDAV client is not installed by default.\


The feature to install on Windows Server is WebDAV Redirector. This feature can be installed via Server Manager or using PowerShell.

To install with PowerShell, `Install-WindowsFeature WebDAV-Redirector –Restart`. The server needs to reboot for the installation to complete.

After reboot, the installation can be verified with the following PowerShell command, `Get-WindowsFeature WebDAV-Redirector | Format-Table –Autosize`.

![Screenshot showing the command prompt used to verify the installation of WebDAV Redirector](https://assets.tryhackme.com/additional/sysinternals/win2019-webclient1.png)\


The same process as with a Windows 10 client applies from this point:

* Make sure the WebClient service is running
* Make sure Network Discovery is enabled

Now with all the necessary components installed and enabled the local machine is ready to run Sysinternals tools from the web.&#x20;

There are 2 ways the tools can be run:

* Run the tool from the command line (as shown above from the Windows 10 machine)
* Create a network drive and run the tool from the mapped drive

Method 1 - Run tool from command line

![Screenshot showing a Sysinternals tool started from the command line](https://assets.tryhackme.com/additional/sysinternals/win2019-method1.png)\


Method 2 - Run tool from a mapped drive

![Screenshot showing how drive Y is connected to live.sysinternals.com\tools](https://assets.tryhackme.com/additional/sysinternals/win2019-method2a.png)

Note: The asterisk will auto-assign a drive letter. The asterick can be replaced with an actual drive letter instead.

![Screenshot showing drive Y among the Network locations](https://assets.tryhackme.com/additional/sysinternals/win2019-method2b.png)\


The website is now browsable within the local machine.

![Screenshot browsing drive Y via the command prompt](https://assets.tryhackme.com/additional/sysinternals/win2019-method2c.png)\


![Screenshot showing the help page launched from the command prompt for the Process Monitor tool.](https://assets.tryhackme.com/additional/sysinternals/win2019-method2d.png)\


Now that we got that out of the way time to start exploring some of these tools.
