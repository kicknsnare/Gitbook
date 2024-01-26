# Event IDS Cheat Sheet

<pre class="language-powershell"><code class="lang-powershell">#Successful Account Logon:
Event ID 4624
#Failed Account Logon:
Event ID 4625
#Account Logon - Kerberos Authentication:
Event ID 4768
#Account Logon - NTLM Authentication:
Event ID 4776
#New Process Creation:
Event ID 4688
#User Account Changes:
Event ID 4738
#Security Group Membership Changes:
Event ID 4728 (Group Created)
Event ID 4732 (Group Member Added)
Event ID 4756 (Group Member Removed)
#Privilege Use:
Event ID 4672 (Special privileges assigned to a new logon)
#Account Lockout:
Event ID 4740
#Service Installation:
Event ID 4697
#Scheduled Task Creation:
Event ID 4700
#Policy Change:
Event ID 4719 (System audit policy changed)
#Clearing of the Security Log:
Event ID 104
Event ID 1102 (Log cleared)
<strong>#Detection of Malicious PowerShell Activity:
</strong>Event ID 4104 (PowerShell module logging)
Event ID 4105 (PowerShell pipeline execution details)
#Network Connection Events:
Event ID 5156 (Filtering Platform Connection)
Event ID 5158 (Filtering Platform Connection)
#Windows Firewall Rule Changes:
Event ID 2004 (Firewall rule added)
Event ID 2006 (Firewall rule deleted)
#File and Folder Access:
Event ID 4663 (An attempt was made to access an object)
#Audit Policy Changes:
Event ID 4718 (System audit policy changes)
</code></pre>
