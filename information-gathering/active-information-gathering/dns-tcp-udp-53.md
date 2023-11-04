# DNS - TCP/UDP 53

### Find IP address of a website

```
host www.megacorpone.com
```

### Search for different types of DNS records

```
host -t <record type e.g. mx> megacorpone.com
```

### BruteForce foward lookup zones

```
for ip in $(seq  50 100); do host 38.100.193.$ip; done | grep -v "not found"
```

### Test for zone transfers

```
host -l megacorpone.com ns2.megacorpone.com
dig axfr @<ip address> <FQDN>
```

### Enumerate nameservers for a domain

```
host -t ns megacorpone.com | cut -d " " -f 4
```
