# FTP - TCP-21

###

## Note

* Sometimes clues are put here.
* Old version of ftp might be vulnerable
* Look at the version
* Search the exploit using Google / Searchsploit / Rapid7
* If you find some credential, try it on SSH / Login page / database

{% hint style="info" %}
Many ftp-servers allow anonymous users. `anonymous:anonymous`
{% endhint %}

### Connection

```
ncftp $ip
ftp $ip
```

### Scan for vulnerabilites with Nmap

```
nmap --script=ftp-* -p 21 <target ip>
```

### Grab FTP banner with NC

```
nc -nv <target ip> 21
```

### Check if anonymous login is enabled

```
ftp <target ip> 21
anonymous:anonymous
```

### Bruteforce FTP login with Hydra

```
hydra -l <username> -P /opt/wordlists/rockyou.txt ftp://<target ip>
```

```
hydra -l $user -P /usr/share/wordlistsnmap.lst -f $ip ftp -V
```

```
medusa -h $ip -u $user -P passwords.txt -M ftp///
```

### Enumeration of users&#x20;

```
ftp-user-enum.pl -U users.txt -t $ip
```

```
ftp-user-enum.pl -M iu -U users.txt -t $ip
```

### Commands

```
send # Send single file
put # Send one file.
mput # Send multiple files.
mget # Get multiple files.
get # Get file from the remote computer.
ls # list 
mget * # Download everything

binary = Switches to binary transfer mode.
ascii = Switch to ASCII transfer mode
```

### Configuration files

```
ftpusers
ftp.conf
proftpd.conf
```

### Vulnerable Versions

* ProFTPD-1.3.3c Backdoor
* ProFTPD 1.3.5 Mod\_Copy Command Execution
* VSFTPD v2.3.4 Backdoor Command Execution
