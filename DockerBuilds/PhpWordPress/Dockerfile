FROM php:7.2-apache

# Actualizo el contenido de los repositorios
RUN apt update


# Instalo ciertas herramientas que necesito para probar cosas

# Editor de texto
RUN apt install -y nano

# Herramienta para hacer pings a los otros contenedores
RUN apt install -y iputils-ping


# Git por si quiero clonar algún repositorio para probar
RUN apt install -y git

# Un cliente de base de datos (mysql/mariadb) por si quiero realizar pruebas de permisos 
# desde el host del servidor web
RUN apt install -y  mycli

# Ejecutamos la herramienta del contenedor para instalar el módulo mysqli 
# que es necesario para la mayoría de aplicaciones actuales
RUN docker-php-ext-install mysqli
 

# Cambio el directorio de trabajo al directorio raíz de Apache
WORKDIR /var/www/html

RUN git clone https://github.com/WordPress/WordPress.git


# Cambio los permisos del directorio recién creado
RUN chown -R www-data:www-data /var/www/html/WordPress
