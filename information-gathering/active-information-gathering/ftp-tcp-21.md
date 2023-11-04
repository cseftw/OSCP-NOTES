# FTP - TCP-21

### Scan for vulnerabilities with Nmap

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
