## Configuracion de un Ubuntu Minimal desde cero.

## Es importante si estamos en una maquina virtual tenerlo en adaptador puente
sudo apt install net-tools

## Primero necesitamos tener instalado SSH
sudo apt install ssh
sudo nano /etc/ssh/sshd_config      --Cambiamos el puerto
sudo systemctl restart ssh          --Resetea el servicio ssh

--Voy por aquí
## Configuracion del firewall
apt-get install ufw     -- Instalas el firewall
ufw enable              -- Activas el firewall y te bloquea todos los puertos
ufw status numbered     -- Para ver las reglas que hemos creado numeradas
ufw allow puerto        -- Abre puerto
