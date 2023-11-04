# SMPTP/s - TCP 25,465,587

### List all available SMTP commands with Nmap

```
nmap -p25 --script smtp-commands <target ip>
```

### Enumerate users with VRFY

```
telnet <target ip> <target port>
HELO x
VRFY root
```

### Enumerate users with RCPT TO

```
telnet <target ip> <target port>
HELO x
MAIL FROM:test@example.com
RCPT TO:root
```

### Enumerate users with EXPN

```
telnet <target ip> <target port>
HELO x
EXPN root
```
