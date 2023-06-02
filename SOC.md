etc/rules/local_rules.xml creas la regla, existen grupos segun lo que haga la regla.

<rule id="100100" level="10" frequency="5">
  <if_matched_sid>20005</if_matched_sid>
  <same_source_ip />
  <description>Windows: 5 failed logins from the same source IP</description>
  <group>authentication_failed,pci_dss_10.2.4,pci_dss_10.2.5,gdpr_IV_35.7.d,gdpr_IV_32.2,</group>
</rule> 


luego en etc/ossec.conf creas el active response 


Para bloquear IP por ssh fail nos fijamos en el ID de la regla que salta en esos intentos, creamos un script de bloqueo.




 var/ossec/etc/ossec.conf


![imagen](https://github.com/dojetin/Cheatsheet/assets/102966393/044dfe54-17e9-4108-ab96-0e709dc66eb9)
[Descarga.txt](https://github.com/dojetin/Cheatsheet/files/11591410/script.1.txt)


 var/ossec/active-response/bin es donde se guarda el script

![imagen](https://github.com/dojetin/Cheatsheet/assets/102966393/e0ddcdb9-bfc6-41a0-a698-be5af8e3ae25)
[Descargalo.txt](https://github.com/dojetin/Cheatsheet/files/11591408/script.txt)


chmod 750 nombredelarchivo 

chown root:wazuh nombre

systemctl restart wazuh-manager

En esta carpeta se nos ha guardado el log de bloqueos de ip y podemos verificar si ha funcionado
![imagen](https://github.com/dojetin/Cheatsheet/assets/102966393/44e21a32-2de9-4b61-838c-b9380963a03c)



Con esta configuracion seria para el agente 001

<ossec_config>
  <active-response>
    <disabled>no</disabled>
    <command>host-deny</command>
    <location>defined-agent</location>
    <agent_id>001</agent_id>
    <level>10</level>
    <timeout>180</timeout>
  </active-response>
</ossec_config>


con crontab -l puedes mirar las tareas que estan programando
con crontab -e puedes editar las tareas existentes
*/5 * * * * /ruta/al/script.sh    (con eso se ejecutaria cada 5 minutos)
0 */6 * * * /var/ossec/etc/rotateAPIkey.sh   (cada 6 horas)
0 */6 * * * /home/rocky/lanzador.sh   (cada 6 horas)

[rotateAPIkey.txt](https://github.com/dojetin/Cheatsheet/files/11634405/rotateAPIkey.txt)


/home/rocky/lanzador.sh                                                                                                 
#!/bin/bash

bash /var/ossec/etc/lists/downList.sh
bash /var/ossec/etc/lists/watcher.sh
bash /var/ossec/etc/rotateAPIkey.sh
