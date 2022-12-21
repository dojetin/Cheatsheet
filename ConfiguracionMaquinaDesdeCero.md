## Configuracion de un Ubuntu Minimal desde cero.

## Es importante si estamos en una maquina virtual tenerlo en adaptador puente
sudo apt install net-tools

## Primero necesitamos tener instalado SSH
sudo apt install ssh
sudo nano /etc/ssh/sshd_config      --Cambiamos el puerto
sudo systemctl restart ssh          --Resetea el servicio ssh

# Instalar aplicación web en Linux [WordPress]

## Actualizo repos
sudo apt-get update -y && sudo apt-get upgrade -y

## Instalo Apache
sudo apt install apache2 -y

## Abro el puerto para Apache
sudo ufw app list

## Instalo MySQL Server
sudo apt install mysql-server -y
mysql -u root
	CREATE DATABASE wordpress DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;
	CREATE USER 'wordpressuser'@'%' IDENTIFIED WITH mysql_native_password BY 'fesac1235';
	GRANT ALL ON wordpress.* TO 'wordpressuser'@'%';
	FLUSH PRIVILEGES;

## Instalo PHP
sudo apt install php libapache2-mod-php php-mysql php-curl php-gd php-xml php-mbstring php-xmlrpc php-zip php-soap php-intl -y

## Descargar WordPress
wget https://es.wordpress.org/latest-es_ES.zip
unzip latest-es_ES.zip ^C
mv wordpress/ /var/www/html/
sudo chown -R www-data:www-data /var/www/html/wordpress


## Ponemos IP fija  mejor no hacerlo
sudo cd /etc/netplan o sudo nano /etc/network/interfaces

Configuración de dirección IP fija para el interfaz eth0
auto eth0
iface eth0 inet static
address 192.168.1.50
netmask 255.255.255.0
network 192.168.1.0
broadcast 192.168.1.255
gateway 192.168.1.1

sudo netplan apply

--Voy por aquí

## Configuracion del firewall
apt-get install ufw     -- Instalas el firewall
ufw enable              -- Activas el firewall y te bloquea todos los puertos
ufw status numbered     -- Para ver las reglas que hemos creado numeradas
ufw allow puerto        -- Abre puerto


## USB en un VBOX
.                         --Introduces el usb 
fdisk -l                  --Te muestra los discos que tienes insertados entre ellos el USB 
mkdir usb                 --Creas una carpeta
mount /dev/sdb2 /mnt/usb  --Montas el usb en esa carpta y cualquier cosa que copies dentro se guarda
unmount /dev/sdb2




