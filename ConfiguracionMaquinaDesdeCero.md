## Configuracion de un Ubuntu Minimal desde cero.

## Es importante si estamos en una maquina virtual tenerlo en adaptador puente
sudo apt install net-tools

## Primero necesitamos tener instalado SSH
sudo apt install ssh
sudo nano /etc/ssh/sshd_config      --Cambiamos el puerto
sudo systemctl restart ssh          --Resetea el servicio ssh

## Ponemos IP fija
sudo nano /etc/network/interfaces
# Configuración de dirección IP fija para el interfaz eth0
auto eth0
iface eth0 inet static
address 192.168.1.50
netmask 255.255.255.0
network 192.168.1.0
broadcast 192.168.1.255
gateway 192.168.1.1

--Voy por aquí

## Configuracion del firewall
apt-get install ufw     -- Instalas el firewall
ufw enable              -- Activas el firewall y te bloquea todos los puertos
ufw status numbered     -- Para ver las reglas que hemos creado numeradas
ufw allow puerto        -- Abre puerto
