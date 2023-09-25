### Volúmenes en Docker Apache
## 1.- Descarga la imagen 'httpd' y comprueba que está en tu equipo.
Nada extraño, docker run -dit (--name elquequieras) httpd:2.4
## 2.- Crea un contenedor con el nombre 'dam_httpd'.
Véase arriba y cambiar elquequieras por dam_httpd.
## 3.- Mapea el puerto 80 del contenedor con el puerto 8000 de tu máquina.
tras poner --name dam_httpd, pon -p 8000(el puerto de tu pc):80(el puerto http del contenedor) y luego httpd:2.4
## 4.- Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas. 
Antes de hacer el nuevo contenedor para ello, haz un cd a la ubicación que quieres dejar el volumen de apache. 
Una vez hayas hecho eso, pon tras -p 8000:80 esta flag: -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ y el httpd:2.4
## 5.-Realiza un 'hola mundo' en html y comprueba que accedes desde el navegador.
En la locación en la que hayas hecho el volumen, aparecerá una carpeta htdocs si haces un ls en la terminal.
Ve a esa carpeta y haz un sudo touch index.html. Haz una hola mundo básico en html y guarda el resultado.
## 6.- Crea un volumen para este mismo fin.
Eso mismo has hecho. Para ver el servidor apache, pon localhost:8000 en tu navegador de preferencia.
## 7.- Crea un contenedor 'dam_web1' que use este volumen para el 'htdocs'
Repite los pasos 1 a 5, solo asegúrate de que estés haciendo el volúmen en la misma carpeta que el contenedor anterior.
## 8.- Utiliza Code para hacer un hola mundo en html
Repita el paso 5.
## 9.- Crea otro contenedor 'dam_web2' con el mismo volumen y a otro puerto, por ejemplo 9080.
Repite los pasos 1 a 5 otra vez, solo pon -p 9080:80 en su lugar.
## 10.- Comprueba que los dos servidores 'sirven' la misma página, es decir, cuando consultamos en el navegador: 
Asegúrate de que tus contenedores están encendidos y pon 2 pestañas de tu navegador de preferencia donde esten sus puertos puestos en el localhost.
(Es decir, el 8000 en una pestaña y el 9080 en la otra.)
## 11.- Tienen que salir la misma página web
Enhorabuena si lo has logrado.