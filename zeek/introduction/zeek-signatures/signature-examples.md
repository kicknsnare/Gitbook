# Signature Examples

```bash
signature http-password {
     ip-proto == tcp
     dst-port == 80
     payload /.*password.*/
     event "Cleartext Password Found!"
}

# signature: Signature name.
# ip-proto: Filtering TCP connection.
# dst-port: Filtering destination port 80.
# payload: Filtering the "password" phrase.
# event: Signature match message.
```

<mark style="color:blue;">Once the match occurs, Zeek will generate an alert and create additional log files (signatures.log and notice.log).</mark>

<figure><img src="https://camo.githubusercontent.com/1470c5018e821a1e3f2b8a95f2fd410d6c86c69508970700db0d2015ee6e1dc6/68747470733a2f2f692e696d6775722e636f6d2f69464f475a496b2e706e67" alt=""><figcaption></figcaption></figure>



## FTP bruteforce signature

```bash
signature ftp-admin {
     ip-proto == tcp
     ftp /.*USER.*dmin.*/
     event "FTP Admin Login Attempt!"
}

```

```bash
signature ftp-username {
    ip-proto == tcp
    ftp /.*USER.*/
    event "FTP Username Input Found!"
}

signature ftp-brute {
    ip-proto == tcp
     payload /.*530.*Login.*incorrect.*/
    event "FTP Brute-force Attempt!"
}
```
