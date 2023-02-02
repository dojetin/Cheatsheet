# RoadMap Pentest

- [ ] RECONOCIMIENTO
	- [ ] NMAP general (de todos los puertos) para localizar puertos expuestos 
		- [ ] nmap -p- 192.168.1.200 --min-rate 4000
	- [ ] NMAP más directo que identifique servicios y versiones solo de los abiertos
		- [ ] nmap -sS -sC -sV -O -p21,22,80,443,3389 192.168.1.200
	- [ ] Identificación de servicios con vulns (searchExploit o ExploitDB o Google)
	- [ ] En función de las vulns buscar medio de exploitación 
	- [ ] Ejecutar algún script de nmap 
		- [ ] nmap 192.168.1.200 --script vuln
- [ ] EXPLOTACIÓN
	- [ ] También puedo usar Metasploit
	- [ ] Según sea la vuln podrás suber una shell, o avanzar un privilegio
