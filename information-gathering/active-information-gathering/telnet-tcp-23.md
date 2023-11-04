# Telnet - TCP 23

## SMTP Banner grabbing through telnet

```
telnet $ip 25
```

```
vrfy admin@mail.lab.ignite
```

**If you received a message code 250,251,252 which means user account is valid.**

## Nmap enumeration

```
nmap -p 23 --script=telnet-ntlm-info.nse
```

## Configuration files

```
/etc/inetd.conf
/etc/xinetd.d/telnet
/etc/xinetd.d/stelnet
```

## BruteForce Attack

```
hydra -l root -P /usr/share/wordlists/seclists/Passwords/10_million_password_list_top_100.txt $ip telnet
```

## Exploitation

* Gather version numbers
* Searchsploit
* Default Creds
* Creds previously gathered
* Download the software
