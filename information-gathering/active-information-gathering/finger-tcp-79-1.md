# Finger - TCP 79

## Find logged in users on target .

```
finger @$ip
```

## Check user is existed or not&#x20;

```
finger USERNAME@$ip
```

## Finger-user-enum

```
cd /tmp/
wget http://pentestmonkey.net/tools/finger-user-enum/finger-user-enum-1.0.tar.gz
tar -xvf finger-user-enum-1.0.tar.gz
cd finger-user-enum-1.0
perl finger-user-enum.pl -t 10.22.1.11 -U /tmp/rockyou-top1000.txt
```
