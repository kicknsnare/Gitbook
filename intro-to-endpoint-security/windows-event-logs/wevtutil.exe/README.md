# wevtutil.exe

Tool for making filters for logs

```powershell
wevtutil.exe /?
# This will provide additional information specific to a command:
wevtutil COMMAND /?

wevtutil qe Application /c:3 /rd:true /f:text
#Application, the logs from you want to query
#c:3, amount of logs you want to display
#rd:true, you want the lastest events, if false it displays the first logs
#f:text prints the logs in easy format to read
wevtutil qe 
```
