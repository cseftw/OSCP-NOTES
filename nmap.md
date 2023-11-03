---
description: This page belongs to My nmap scans command
---

# Nmap

## NMAP Script scan&#x20;

```bash
sudo nmap -sC -sV -A - $IP
```

## NMAP TCP SCAN

```
sudo nmap -sS -p- -Pn $IP
```

## NMAP UDP SCAN

```
sudo nmap -sU $IP
```
