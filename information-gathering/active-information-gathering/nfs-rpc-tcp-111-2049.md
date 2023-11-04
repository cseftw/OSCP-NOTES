# NFS/RPC - TCP 111, 2049

### Note :-

```
# Check UID of mounted share and make a user with the same UID and group memberships to access the mounted share locally.
sudo useradd dummy; sudo usermod -u 2017 dummy; sudo usermod -a -G www-data dummy
```

### Check if services are registered with RPCbind

```
nmap -sV -p 111 --script=rpcinfo <ip range>
```

### Enumerate NFS with Nmap

```
nmap -p 111 --script nfs* <target ip>
```

### Mount an NFS share

```
mkdir /tmp/home
sudo mount -o nolock <target ip>:/home /tmp/home/
```

### Show available mounts on a system

```
showmount -e <target ip>
```

### Bypass ACL with nfspy

```
Script src: https://github.com/bonsaiviking/NfSpy
sudo nfspysh -o server=<target ip>:/home
```
