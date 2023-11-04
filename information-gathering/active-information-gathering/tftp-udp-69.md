# TFTP - UDP 69

**Vulnerable versions**

```
Version 1.3, 1.4, 1.9, 2.1
```

**List of available commands**

```
send # Send single file
put # Upload one file
mput # Upload multiple files
mget # Get multiple files
get # Get a single file
ls # list 
mget * # Download everything

binary = Switches to binary transfer mode
ascii = Switch to ASCII transfer mode
```

**Scan for vulnerabilities with Nmap**

```
sudo nmap -sU -p 69 --script tftp-enum.nse <target ip>
```
