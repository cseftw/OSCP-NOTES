# (MS)RPC

## Enumerate , shows if any NFS mount exposed :&#x20;

```
rpcinfo -p $ip
```

```
nmap $ip --script=msrpc-enum
```

```
nmap -n -v -sV -Pn 192.168.0.101 --script=msrpc-enum
```

## Connection

**Connect to an RPC share without a username and password and enumerate privelage**

```
rpcclient --user="" --command=enumprivs -N $ip
```

**Connect to an RPC share with a username and enumerate privleage**

```
rpcclient --user="<Username>" --command=enumprivs $ip
```

## Command&#x20;

```
rpcclient>srvinfo
rpcclient>enumdomusers
rpcclient>getdompwinfo
```
