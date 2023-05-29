etc/rules/local_rules.xml creas la regla, existen grupos segun lo que haga la regla.

<rule id="100100" level="10" frequency="5">
  <if_matched_sid>20005</if_matched_sid>
  <same_source_ip />
  <description>Windows: 5 failed logins from the same source IP</description>
  <group>authentication_failed,pci_dss_10.2.4,pci_dss_10.2.5,gdpr_IV_35.7.d,gdpr_IV_32.2,</group>
</rule> 


luego en etc/ossec.conf creas el active response 


Para bloquear IP por ssh fail nos fijamos en el ID de la regla que salta en esos intentos, creamos un script de bloqueo.


![imagen](https://github.com/dojetin/Cheatsheet/assets/102966393/e0ddcdb9-bfc6-41a0-a698-be5af8e3ae25)
