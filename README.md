#### Carlos Polop's Hacktricks
https://book.hacktricks.xyz

#### GTFO Bins
Unix binaries that can be abused to ~~get the f**k~~ break out restricted shells, escalate or maintain elevated privileges, transfer files, spawn bind and reverse shells, and facilitate the other post-exploitation tasks.
https://gtfobins.github.io

### Commands

Set IP variable for ease of access.
```bash
IP=<IP>
```
ex:
```bash
IP=10.0.0.0
```
Access it with `$IP`, for example:
```bash
echo $IP
```

#### Fuzzing

Nmap
```bash
nmap -sV -sC --open -v --min-rate 1000 -p- $IP -o nmap-scan.txt
```

Fuzzing for file downloads:
```bash
ffuf -w /usr/share/seclists/Fuzzing/LFI/LFI-Jhaddix.txt:FUZZ -u http://example-url.com/download?file=FUZZ --fs 0`
```

Gobuster: 
```bash
gobuster dir -w /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt -u http://example-url.com -x php,html -o gobuster.txt
```

Other enumeration resources:
https://blog.adithyanak.com/oscp-preparation-guide/enumeration


## Post Exploitation

#### Privilege Escalation Cheat Sheet
https://github.com/rmusser01/Infosec_Reference/blob/master/Draft/Cheat%20sheets%20reference%20pages%20Checklists%20-/Linux/cheat%20sheet%20Basic%20Linux%20Privilege%20Escalation.txt
