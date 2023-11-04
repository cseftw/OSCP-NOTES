# Oracle - TCP 1521

## Nmap Script

```
nmap -p 1521 -A $ip
```

```
nmap -n -v -sV -Pn -p 1521 –script=oracle-enum-users –script-args sid=ORCL,userdb=users.txt $ip
```

## oscanner

```
oscanner -s $ip -P 1521
```

## Fingerprint oracle tns

**tnscmd10g = A tool to prod the oracle tnslsnr process**

```
tnscmd10g version -h 192.168.1.101
tnscmd10g status -h 192.168.1.101
```

## Brute-Force Account

```
nmap --script=oracle-sid-brute $ip
nmap  -n -v -sV -Pn -p 1521 --script=oracle-brute $ip
```
