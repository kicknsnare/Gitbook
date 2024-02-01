# Putting theory into practice Walkthrough

Scenario 1 (Questions 1 & 2): The server admins have made numerous complaints to Management regarding PowerShell being blocked in the environment. Management finally approved the usage of PowerShell within the environment. Visibility is now needed to ensure there are no gaps in coverage. You researched this topic: what logs to look at, what event IDs to monitor, etc. You enabled PowerShell logging on a test machine and had a colleague execute various commands.&#x20;

Scenario 2 (Questions 3 & 4): The Security Team is using Event Logs more. They want to ensure they can monitor if event logs are cleared. You assigned a colleague to execute this action.

Scenario 3 (Questions 5, 6 & 7): The threat intel team shared its research on Emotet. They advised searching for event ID 4104 and the text "ScriptBlockText" within the EventData element. Find the encoded PowerShell payload.&#x20;

Scenario 4 (Questions 8 & 9): A report came in that an intern was suspected of running unusual commands on her machine, such as enumerating members of the Administrators group. A senior analyst suggested searching for "`C:\Windows\System32\net1.exe`". Confirm the suspicion.  &#x20;

Answer the questions below

What event ID is to detect a PowerShell downgrade attack?

&#x20;

<figure><img src="https://camo.githubusercontent.com/00e63600103f4ccbf64cc1c0193cd625a18412f906c0143658b7830f1adb812c/68747470733a2f2f692e696d6775722e636f6d2f4962464f6458422e706e67" alt=""><figcaption></figcaption></figure>

What is the Date and Time this attack took place? (MM/DD/YYYY H:MM:SS \[AM/PM])

&#x20;

<figure><img src="https://camo.githubusercontent.com/5b549396b1c665e44a1500ce68171d9d22b49e077b6efb5f23691cbd343efbcd/68747470733a2f2f692e696d6775722e636f6d2f43496a6b7462512e706e67" alt=""><figcaption></figcaption></figure>

A Log clear event was recorded. What is the 'Event Record ID'?

&#x20;[![](https://camo.githubusercontent.com/b3db915e176600595f25aa68f68e80b3a40ece040c9ecda7892de73d272c2667/68747470733a2f2f692e696d6775722e636f6d2f6c6d756438566c2e706e67)](https://camo.githubusercontent.com/b3db915e176600595f25aa68f68e80b3a40ece040c9ecda7892de73d272c2667/68747470733a2f2f692e696d6775722e636f6d2f6c6d756438566c2e706e67)

&#x20;

<figure><img src="https://camo.githubusercontent.com/47226d4366c9e009ba90dc3cc2ac4d2415eec50a89562ceab4cd414a917759b1/68747470733a2f2f692e696d6775722e636f6d2f536563425152332e706e67" alt=""><figcaption></figcaption></figure>

What is the name of the computer?\
&#x20;

<figure><img src="https://camo.githubusercontent.com/788d4c6c6333a925fa09b6ebbc08ba57b306b13485f8b116d221973c035fe605/68747470733a2f2f692e696d6775722e636f6d2f714c65317450722e706e67" alt=""><figcaption></figcaption></figure>



What is the name of the first variable within the PowerShell command?

&#x20;

<figure><img src="https://camo.githubusercontent.com/45dea2ed82051bbc69e980c9f9ec602b5d02d929465c8e0be073ff6d96923360/68747470733a2f2f692e696d6775722e636f6d2f416e4d316d446a2e706e67" alt=""><figcaption></figcaption></figure>

What is the Date and Time this attack took place? (MM/DD/YYYY H:MM:SS \[AM/PM])\


&#x20;

<figure><img src="https://camo.githubusercontent.com/ef54a7162315b0b98023f677a2e83ddaef8a76bc0a958bf79f74ced8d11d3c25/68747470733a2f2f692e696d6775722e636f6d2f356c61615735372e706e67" alt=""><figcaption></figcaption></figure>

What is the Execution Process ID?

&#x20;

<figure><img src="https://camo.githubusercontent.com/2d7f6e4773e3a2fc26c4ab2d4dceaa2ca5df8c670555cf2f3e4d57114cae8ddc/68747470733a2f2f692e696d6775722e636f6d2f476c693537666f2e706e67" alt=""><figcaption></figcaption></figure>

What is the Group Security ID of the group she enumerated?

&#x20;

<figure><img src="https://camo.githubusercontent.com/9ca7487343c607d514ca479e81dc27e9701cb09b35ff96bce0ebc349423ed8ca/68747470733a2f2f692e696d6775722e636f6d2f4e4e76574636482e706e67" alt=""><figcaption></figcaption></figure>



What is the event ID?

<mark style="color:green;">4799</mark>\
