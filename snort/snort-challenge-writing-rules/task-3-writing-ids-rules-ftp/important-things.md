# Important things

```bash
#Failed login attempts
content:"530 User"/"530"
#Succesful loging attempts
content:"230 User"/"230"
#failed login attempts with a valid username but a bad password or no password.
content:"331 Password"
#failed login attemps + other filter
content:"Administrator"; content:"331 Password"
```
