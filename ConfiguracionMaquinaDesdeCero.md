## Configuracion de un Ubuntu Minimal desde cero.

(Es importante si estamos en una maquina virtual tenerlo en adaptador puente)
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
cd /home/
wget https://es.wordpress.org/latest-es_ES.zip
apt install unzip
unzip latest-es_ES.zip 
mv wordpress /var/www/html


## Si lo vas a configurar por la web 

Nombre de la base de datos:	wordpress
Nombre de usuario:		wordpressuser
Contraseña:			fesac1235
Servidor de la base de datos:	localhost
Prefijo de tabla:		wp_


Título del sitio:		DesviaciónTipica
Nombre de usuario:		davidelete
Contraseña	
•••••••••••••
Tu correo electrónico:		davideletewow@hotmail.es



## Si lo vas a configurar por codigo
nano wp-config-sample.php		Y lo guardas sin el sample
sudo chown -R www-data:www-data /var/www/html/wordpress ## No hacer esto








## Ponemos IP fija  mejor no hacerlo
sudo cd /etc/netplan o sudo nano /etc/network/interfaces

Configuración de dirección IP fija para el interfaz eth0
network:
  version: 2
  renderer: networkd
  ethernets:
    enp0s3:
     dhcp4: no
     addresses: [192.168.15.113/24]
     gateway4: 192.168.1.1
     nameservers:
       addresses: [8.8.8.8,8.8.4.4]

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




