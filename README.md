# Sistemas-operativos

 # *CODIGO NGINX*
 Para configurar nginx como proxy inverso, se edito el archivo de configuración de Nginx (/etc/nginx/nginx.conf) 
 y se agregaron las siguientes líneas:
 server {
    listen 80;
    server_name 192.168.20.25;

    location /compose {
        proxy_pass http://192.168.20.24:8000/;
    }

    location /apache {
        proxy_pass http://192.168.20.23:80/;
    }
}

 
 # *CODIGO DOCKER*
 
Se creo un archivo docker-compose.yml con la siguiente configuración para desplegar una aplicación web:
 
 version: '3'

services:
  web:
    image: nginx
    ports:
      - "8000:80"
 
 # *CODIGO APACHE*
 
 No se necesito codifo 
 
