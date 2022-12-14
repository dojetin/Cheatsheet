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