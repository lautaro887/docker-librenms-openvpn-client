# docker-librenms-openvpn-client
conexion de openvpn a clientes remotos , para monitoreo con librenms .


Archivo docker compose para levantar librenms centralizado para clientes.

#modo de ejecutar 
 sudo docker-compose -p nombrecliente up -d
esto genera un proyecto para cada uno por separado , por lo cual deberemos tener una carpeta para cada implementacion

deberiamos copiar el repositorio en una carpeta para cada implementacion 



#archivo .env 

#TZ=America/Argentina/Mendoza #servidor horario , horas php
#PUID=1000
#PGID=1000

#credenciales mysql (modificar para todos igual)
#MYSQL_DATABASE=librenms 
#MYSQL_USER=librenms
#MYSQL_PASSWORD=asupersecretpassword

#declaracion de redes usadas entre contenedores , a agregar ruta estatica en otro extremo de vpn
#RED_SERVICIO=172.26.0.0/24 # apuntar a esta red desde router servidor , por medio de ruta estatica
#IP_GW_OVPN=172.26.0.254  #gateway usado para la red virtual , solo es para comunicacion entre contenedores y que estos apunten a las redes del otro extremo vpn
#PUERTO=8000 #puerto usado para conectarse a la gestion de librenms
#todos estos parametros se deben cambiar entre cada nueva implementacion , debido a que se pueden superponer  y no va a arrancar.


carpeta vpn
debemos tener alojados los archivos y certificados en la carpeta vpn , el archivo de configuracion ovpn tiene que estar nombrado como client.ovpn , sumado a esto debemos tener un archivo auth.txt , en el cual colocaremos las credenciales para iniciar sesion en la vpn . (usuario creado en servidor ovpn)
