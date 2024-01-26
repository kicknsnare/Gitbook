# Hunting Persistence

We can hunt persistence with Sysmon by looking for File Creation events as well as Registry Modification events. <mark style="color:blue;">**`The SwiftOnSecurity configuration file does a good job of specifically targeting persistence and techniques used`**</mark>

* Any changes to the Start Menu should be investigated.
* We can also filter by the `Rule Name T1023`
*   Just like the startup technique, we can filter by the `RuleName T1060` to make finding the anomaly easier. (Registry)

    \
