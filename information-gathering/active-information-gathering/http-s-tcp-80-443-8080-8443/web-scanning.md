# Web Scanning

## Nmap Script

```
nmap --script=http-enum <host>
```

## Nikto web server scan

```
nikto -h $ip
nikto -h $ip -p 80,8080,1234 #test different ports with one scan
```

```
-Tuning Options
0 – File Upload
1 – Interesting File / Seen in logs
2 – Misconfiguration / Default File
3 – Information Disclosure
4 – Injection (XSS/Script/HTML)
5 – Remote File Retrieval – Inside Web Root
6 – Denial of Service
7 – Remote File Retrieval – Server Wide
8 – Command Execution / Remote Shell
9 – SQL Injection
a – Authentication Bypass
b – Software Identification
c – Remote Source Inclusion
x – Reverse Tuning Options (i.e., include all except specified)
```

```
nikto -Display 1234EP -o report.html -Format htm -Tuning 123bde -host 192.168.0.102
```

## Wordpress scan

```
wpscan -u $ip/wp/
```

## Banner grabbing

```
./whatweb $ip # identifies all known services
```

## Vulnerability scanning

```
nikto -host http://$ip
```

```
nmap --script=http-vuln* $ip
```

## Coldfusion vulnerabilty scanning

```
nmap -v -p 80 --script=http-vuln-cve2010-2861 $ip
```

## Backup files search

```
./bfac --url http://$ip/ --level 4
```

## WebDav

```
davtest -move -sendbd auto -url http://$ip:8080/webdav/
```

```
cadaver http://$ip:8080/webdav/
```

## Uniscan

**1 - LFI, RFI, and RCE vulnerability scanner**

```
uniscan -u http://192.168.1.202/ -qd
```
