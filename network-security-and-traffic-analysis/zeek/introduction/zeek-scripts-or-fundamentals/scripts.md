# Scripts

Here the first, second and fourth lines are the predefined syntaxes of the scripting language. The only part we created is the third line which tells Zeek to extract DHCP hostnames.

```bash
event dhcp_message (c: connection, is_orig: bool, msg: DHCP::Msg, options: DHCP::Options)
{
print options$host_name;
}
```
