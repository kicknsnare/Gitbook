# How to reconstruct a pdf or attachment

* Copy the email html source to other file and edit it. Remove the mime delimeters. Only leave the base64 enconding&#x20;

```bash
cat <copied_file> | base64 -d > <reconstructed_file.extension>
tr -d ‘\n’ < <copied_file> | base64 -d > <reconstructed_file.extension>
```
