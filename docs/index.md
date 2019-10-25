# <center> Manual de Instalación de Proser</center> 
* * *

Este manual va dirigido a la instalación de la aplicación Proser. Este contendrá las instrucciones necesarias para proceder a su instalación. De igual manera, se hará referencia a todos los requisitos y programas necesarios para que la aplicación pueda tener un buen ambiente de trabajo. No obstante, se incluye la preparación del server bien sea en  físico o virtual para proceder a instalar Proser.


##Requisitos antes de instalar Proser

Lo primero que se debe hacer es preparar el servidor de reportería. Para ello se tienen que cumplir los siguientes pasos: 

1) Se debe tener instalado el sistema operativo Centos 7, bien sea en un VirtualBox o en un disco físico. Una vez instalado se debe actualizar.  

2) A continuación, hay que instalar Apache2.  

3) Por consiguiente, se instala MariaDB versión 10.3  

4) Se debe instalar PHP versión 7.2 o mayor.  

5) Luego, hay que instalar Phpmyadmin 4.9.0 o mayor.  

6) Instalar Node versión 10 o mayor.  

7) De igual manera, se debe instalar htop (el se encarga de mostrar la información de los procesos que se  están ejecutando en Centos).  

8) Luego, se tiene que instalar PM2 la última versión.  

9) Instalar SOX en su última versión.  

10) Debemos tener acceso al repositorio de archivos de Proser. Para ello, el Administrador del repositorio nos tiene que dar acceso, mandando una invitación de github.


### Notas: 
* La instalación fue hecha con VirtualBox. De esta manera, se indica el proceso y las instalaciones en dicho programa.
* Las mismas instalaciones hechas en VirtualBox son equivalentes con las de un disco físico.


## Descargar la Iso de Centos 7.

Debemos entrar en la página oficial de Centos: <https://www.centos.org/> . Y luego se debe buscar en la sección de descargas.  

En el caso de no conseguir la versión 7 que es la que necesitamos podemos entrar en la siguiente página en donde encontraremos las versiones de Centos desde la 6 hasta la 8: <http://isoredirect.centos.org/>.  

![Centos7 descargar](img/02-centos7/00.png)  

![Centos7 descargar](img/02-centos7/01.png)

De igual manera, tenemos la siguiente documentación que nos brinda Centos para la descarga de dicho sistema operativo: <https://docs.centos.org/en-US/centos/install-guide/downloading/>.  



Al elegir uno de los enlaces que hay de Centos versión 7, se puede observar que hay varios archivos con diferentes medios de descarga de Centos 7; como DVD ISO, Everything ISO,  Minimal ISO, entre otros. El más recomendado es el DVD ISO.  

![Centos7 descargar](img/02-centos7/02.png)


 Estos son los medios básicos de Centos más destacados:  


**1) DVD ISO:** Esta imagen contiene el instalador, así como un conjunto de todos los paquetes que se pueden instalar durante una instalación interactiva. Esta es la descarga recomendada para la mayoría de los usuarios.

**2) Everything ISO:** Contiene el instalador y todos los paquetes disponibles para CentOS. Esta imagen ISO se puede usar para instalar el sistema con paquetes adicionales (usando un archivo Kickstart y especificando paquetes adicionales en la %packagessección); También se puede utilizar para configurar un espejo local para descargar paquetes. Tenga en cuenta que esta imagen es muy grande y requiere una unidad flash de al menos 16 GB u otro almacenamiento.

**3) Minimal ISO:** Contiene el instalador y un conjunto mínimo de paquetes que se pueden usar para instalar un sistema CentOS muy básico. Luego puede usar Yum para descargar paquetes adicionales de los repositorios de actualizaciones.

Luego de elegir la opción de descarga de la Iso debemos esperar que finalice la descarga y tendremos la imagen Iso de Centos 7.


## Instalar VirtualBox:

Primero debemos descargar el VirtualBox, para ello entraremos en la página oficial de VirtualBox en la sección de descargas:
<https://www.virtualbox.org/wiki/Downloads>. Allí podremos elegir según nuestro sistema operativo el que queremos descargar.  

![virtualBox descargar](img/01-virtualbox/00.png)

Luego de descargarlo, debemos instalarlo. En Linux como es un paquete .deb será fácil de instalar al igual que Windows. Al terminar la instalación podremos buscar en menú el VirtualBox y al abrirlo podemos ver el ambiente de trabajo del VirtualBox.  

![virtualBox descargar](img/01-virtualbox/01.png)


## Instalación de Centos 7
* En esta sección veremos como instalar Centos 7 en nuestra máquina, con dos métodos diferentes (VirtualBox y un usb booteable).

### Desde un Usb Booteable
Esto sería en el caso de querer instalar Centos 7 en un disco físico. Debemos seguir los siguientes pasos:

* Tener un pendrive ya formateado, la imagen Iso de Centos 7 y un programa de booteo como Rufus o Universal usb, entre otros.  
  
* Luego, debemos colocar el pendrive en el puerto usb de la computadora y abrir el programa de booteo, en el caso de Rufus, el reconoce el dispositivo usb de una vez, y lo selecciona automáticamente, solo debemos elegir la imagen iso, darle click en empezar y el booteara el pendrive.

* Al terminar el proceso, el pendrive estará listo para instalar Centos 7.

* Para la instalación se debe tener el pendrive en el puerto usb con la computadora apagada, luego se debe prender y al momento que inicie seleccionar la configuración de la computadora para arrancar la máquina desde el usb.

* En ese momento la pc arrancará desde el usb y la instalación de Centos 7 empezará. Solo debes seguir los pasos y ver la configuración, en cuanto a la fecha, hora, red, tipo de instalación, entre otras cosas.


### Desde VirtualBox 
En el caso de VirtualBox se debe configurar para la instalación de Centos 7 en cuanto al espacio del disco virtual, la memoria ram entre otros. A continuación se darán los pasos para su instalación:

* Al abrir el programa de VirtualBox se debe dar click en donde dice Nuevo ya que se hará un nuevo servidor virtual.

* Allí  aparecerá una nueva pestaña en donde hay que escribir el nombre del servidor y automáticamente colocará el tipo y versión de sistema.

![centos7 instalación](img/02-centos7/03.png)

* Por consiguiente, pedirá cuanta memoria ram queremos, además de cuánto es lo recomendado (1024 MB, es decir 1 GB).  

![centos7 instalación](img/02-centos7/04.png)

* Luego, se hará mención del tipo de disco duro. En el cual  hay que elegir el de **crear un disco virtual ahora**.

![centos7 instalación](img/02-centos7/05.png)

* Por consiguiente, el tipo de archivo del disco duro, que sería: VDI(VirtualBox Disk Image).  

![centos7 instalación](img/02-centos7/06.png)

* Después, se elige el almacenamiento en unidad de disco duro física que es la opción de **Reservado Dinámicamente**.  

![centos7 instalación](img/02-centos7/07.png)

* Luego  pedirá la ubicación del archivo y su tamaño. El tamaño  puede ser de 8GB en adelante. 

![centos7 instalación](img/02-centos7/08.png)  

* Al darle click al botón de crear, aparecerá una ventana en donde se especifica la configuración del servidor virtual. Se buscará la opción de Almacenamiento y en la sección de dispositivos de almacenamiento (que aparece en el centro), se podrá ver abajo de Controlador: IDE un icono de disco que dice vacío al cual hay que darle click, y al lado derecho, en la sección de Atributos en unidad óptica habrá un disco de color azul al darle click podemos buscar la imagen Iso de Centos 7.Después de seleccionarla se le da a la opción de aceptar.  

![centos7 instalación](img/02-centos7/09.png)  

* Allí aparecerá un tipo de terminal que tiene por título CentOS 7 y a la opción de Install Centos 7 se le dará enter.  

![centos7 instalación](img/02-centos7/10.png)  

* Al cargar aparecerá la ventana de instalación de Centos 7 con las opciones de lenguaje en donde se elegirá el que convenga dependiendo de la región.  

![centos7 instalación](img/02-centos7/11.png)  

* Luego se verá el Resumen de la Instalación, en donde se puedes modificar la regionalización, el software y el sistema. Se debe dar click en Destino de la instalación, y allí se verá el tamaño de disco virtual que asignamos al sistema operativo, solo hay que dar click en la parte superior izquierda en donde dice listo.  

![centos7 instalación](img/02-centos7/12.png)  
![centos7 instalación](img/02-centos7/13.png)  

* Se puede modificar la opción de red, y también la de selección de software, es decir si quieres una instalación mínima o de otro tipo. Y luego puedes dar click en empezar instalación.  

![centos7 instalación](img/02-centos7/14.png)  

* Al empezar la instalación se debe crear un usuario y una contraseña de root, para ello das click en creación de usuario y se llenan los campos con el nombre de usuario y la contraseña, para así crear el usuario. Luego se da clic en contraseña de root y se crea. Luego hay que esperar que se instale.  

![centos7 instalación](img/02-centos7/15.png)  
![centos7 instalación](img/02-centos7/16.png)  

* Al finalizar la instalación te pedirá que la reinicies, así que se le da a la opción de reiniciar. Y después de reiniciar se verá la terminal con dos opciones de Centos 7, se debe elegir la primera con un enter.  

![centos7 instalación](img/02-centos7/17.png)  

* Después de dar click, se debe aprobar la licencia, para ello se da click en la opción de License Information y se aceptan los términos.

![centos7 instalación](img/02-centos7/18.png)  
![centos7 instalación](img/02-centos7/19.png)  

* Luego, aparecerá el Centos 7 instalado. Se recomienda instalar la opción de Escritorio Gnome, si se instala con la opción de instalación mínima solo podrás  ver la terminal de Centos 7.  

![centos7 instalación](img/02-centos7/20.png) 

* Por último, debes actualizar Centos 7, para ello escribes en la terminal:  su (para entrar como superusuario). Después escribes: **`yum upgrade -y`**(para actualizar todos los paquetes de Centos 7).  

![centos7 instalación](img/02-centos7/21.png)  
![centos7 instalación](img/02-centos7/22.png) 

## Instalación Apache 2
Vamos a ver cómo instalar Apache en CentOS 7, concretamente sobre un servidor recién preparado desde la versión minimal.La instalación del servidor web se realizará usando los paquetes oficiales de la distribución, a través de yum.

En primer lugar actualizamos los paquetes instalados en el sistema, como buena práctica antes de instalar cualquier nueva colección de paquetes:  

```
sudo yum update -y
```  



A continuación instalamos el paquete httpd, que es el que contiene Apache:  

```
sudo yum install httpd -y 
```  

![Apache2 instalación](img/00-apache.png) 

Si queremos saber qué versión exacta de Apache estamos instalando en CentOS 7 usamos el comando httpd:  

```
httpd -v  
```  

![Apache2 instalación](img/01-apache.png)

Para comprobar que el Apache está corriendo ejecutamos el siguiente comando:  

```
systemctl status httpd
```

Y si queremos iniciar el servicio y hacer que lo haga también en cada inicio del sistema, para no tener que iniciarlo manualmente, podemos configurar el inicio del servicio con:  

```
sudo systemctl enable httpd
```

Y así podemos iniciar el servicio httpd por primera vez:  

```
sudo systemctl start httpd
```  

 

## Instalación de MariaDB 10.3

Cree un nuevo archivo de repositorio /etc/yum.repos.d/mariadb.repoy agregue el siguiente código cambiando la url base de acuerdo con la versión y la arquitectura del sistema operativo.  


**`vi /etc/yum.repos.d/mariadb.repo`**  

```
[mariadb]
name = MariaDB
baseurl = http://yum.mariadb.org/10.3/centos73-amd64/
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
```

Usaremos el siguiente comando para instalar MariaDB 10.3:  

```
yum install MariaDB-server MariaDB-client
```  

![mariadb instalación](img/02-mariadb.png)


Una vez que se realiza la instalación, puede iniciar y habilitar MariaDB para que se ejecute en el arranque del sistema ejecutando los siguientes comandos:  

```
systemctl start mariadb
systemctl enable mariadb
```

Para establecer la contraseña raíz de MariaDB, ejecute el comando a continuación. Reemplace nueva contraseña con su contraseña.  

```
mysqladmin -u root password 'new-password'
```  

![Apache2 instalación](img/03-mariadb.png)  

La contraseña también se puede establecer utilizando el script de seguridad MariaDB.MariaDB se entrega con un simple script de seguridad MariaDB, **mysql_secure_installation** , que básicamente le permite eliminar bases de datos de prueba y usuarios anónimos creados por defecto. Esto es muy recomendable para servidores de producción. Este script se puede ejecutar simplemente como:  

```
mysql_secure_installation
```  

![Apache2 instalación](img/04-mariadb.png) 

 El primer aviso sería establecer la contraseña de root. sin embargo, si lo configuró anteriormente, simplemente ingrese la contraseña y continúe.


## Instalación PHP 

### Configurar el repositorio de Yum

En primer lugar, se debe habilitar los repositorios Remi y EPEL yum en su sistema. Use el siguiente comando para instalar el repositorio EPEL en sus sistemas CentOS y Red Hat 7/6. Use este comando para instalar el repositorio EPEL yum en su sistema:  


```
sudo yum install epel-release
```

Ahora ejecute uno de los siguientes comandos según la versión de su sistema operativo para instalar el repositorio Remi:  

```
sudo rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm 
```

### Instalación de PHP 7.3
Su sistema está preparado para la instalación de PHP desde repositorios de yum. Utilice uno de los siguientes comandos para instalar PHP 7.3 o PHP 7.2 o PHP 7.1 en su sistema según sus requisitos.

```
### Install PHP 7.3 
  yum --enablerepo=remi-php73 install php
### Install PHP 7.2 
  yum --enablerepo=remi-php72 install php
### Install PHP 7.1 
  yum --enablerepo=remi-php71 install php
```  

Ahora ejecuta el siguiente comando para verificar la versión actual de PHP activa en mi sistema:  

**`php -v`**  

![php instalación](img/05-php.png) 

 
### Instalar módulos de PHP
También es posible que necesite instalar módulos PHP adicionales según los requisitos de su aplicación. El siguiente comando instalará algunos módulos PHP más útiles:  

```
### Para PHP 7.3
 yum --enablerepo=remi-php73 install php-xml php-soap php-xmlrpc php-mbstring php-json php-gd php-mcrypt
### Para PHP 7.2
 yum --enablerepo=remi-php72 install php-xml php-soap php-xmlrpc php-mbstring php-json php-gd php-mcrypt
### Para PHP 7.1
 yum --enablerepo=remi-php71 install php-xml php-soap php-xmlrpc php-mbstring php-json php-gd php-mcrypt
```

Puede ejecutar el siguiente comando para buscar otros módulos PHP disponibles en repositorios yum configurados:  

```
yum --enablerepo=remi-php73 search php | grep php73 
```


## Instalación de Phpmyadmin

### Habilitar Remi Repository
El paquete más actualizado de phpMyAdmin está disponible en el repositorio de Remi. Instálelo en su sistema utilizando los siguientes comandos.  

```
### CentOS/RHEL 7 ###
rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm
```

Después de habilitar el repositorio Remi en su sistema, comencemos con la instalación de phpMyAdmin usando el administrador de paquetes yum. Todas las dependencias se instalarán automáticamente.  

```
yum --enablerepo = remi, remi-test  Instalar en pc phpMyAdmin
```

### Configurar PhpMyAdmin
phpMyAdmin por defecto solo puede acceder desde localhost. Si desea que sea accesible desde computadoras remotas, edite el archivo de configuración de Apache de phpMyAdmin.  

```
sudo vi /etc/httpd/conf.d/phpMyAdmin.conf
```

Ahora verifique la sección a continuación. Cambiar Requerir local para Requerir todo otorgado, esto deshabilitará el acceso de restricción local y phpMyAdmin estará accesible desde la red.Después de actualizar el archivo de configuración phpMyAdmin Apache, reinicie el servicio Apache para volver a cargar la nueva configuración.  

```
Alias /phpMyAdmin /usr/share/phpMyAdmin
Alias /phpmyadmin /usr/share/phpMyAdmin
 
<Directory /usr/share/phpMyAdmin/>
   AddDefaultCharset UTF-8
 
   <IfModule mod_authz_core.c>
 	# Apache 2.4
 	Require all granted
   </IfModule>
   <IfModule !mod_authz_core.c>
 	# Apache 2.2
 	Order Deny,Allow
 	Deny from All
 	Allow from 127.0.0.1
 	Allow from ::1
   </IfModule>
</Directory>
```
 
Por último, se puede acceder a phpMyAdmin en un navegador utilizando la siguiente URL:

**<span style="color:blue">http://localhost/phpMyAdmin/</span>**  

![phpmyadmin instalación](img/06-phpmyadmin.png)  
![phpmyadmin instalación](img/07-phpmyadmin.png) 


## Instalación de htop

El comando htop es una herramienta que sirve para poder monitorear el estado de tu equipo o servidor, te muestra métricas sobre el estado de la memoria, el porcentaje de uso de los CPUs, el número de procesos corriendo, así como una lista de los procesos que tiene más consumo de recursos. Sin duda htop es una herramienta útil para ver rápidamente y de forma esquemática lo que sucede en tu equipo.  

Para instalar htop en Centos es necesario agregar el repositorio EPEL, que es un conjunto de paquetes de software de alta calidad que pueden ser usados con toda confianza en RHEL, Centos y Scientific Linux.   

Para poder instalar este repositorio hay que seguir los siguientes pasos:  

```
wget http://mirror.pnl.gov/epel/7/x86_64/e/epel-release-7-5.noarch.rpm  

rpm -Uvh epel-release-7-5.noarch.rpm
```

Una vez que tengas instalado el repositorio EPEL en centos 6 o centos 7 puedes instalar el comando htop con la siguiente instrucción:  

```
yum install htop
```

Una vez que tengas instalado el paquete puedes usar el comando htop simplemente tecleando el comando en una terminal, así:  

* **`htop`**  

 
Y verás una gráfica con las que podrás observar el estado de tu servidor.  

![htop instalación](img/08-htop.png) 


## Instalación de Node

Node.js es un tiempo de ejecución de JavaScript integrado en el motor V8 JavaScript de Chrome. Para instalar Node.js 10.x LTS en CentOS 7 , use las distribuciones binarias NodeSource:  

```
curl -sL https://rpm.nodesource.com/setup_10.x | bash  
```   

![node instalación](img/09-node.png) 

Este comando configurará el repositorio Node.js RPM por usted. Todo lo que necesita hacer a continuación es instalar el nodejs paquete, con los siguientes comandos:  

```
 sudo yum clean all && sudo yum makecache rápido  

 sudo yum install -y gcc-c ++ make  

 sudo yum install -y nodejs  
```

Para saber la versión de node solo debemos escribir el siguiente comando:

* **`node -v`**  


## Instalación de PM2.

PM2 es un gestor para el servidor node.js. Te permite gestionar tus aplicaciones node.js, ver los logs, el estado de tus aplicaciones, etc.  

Para instalar el programa escribe los siguientes 3 comandos en tu consola de Centos 7:  

```
 npm install -g pm2  

 pm2 completion install  

 npm install pm2 -g && pm2 update  

```  

## Instalación de Sox

SoX (Sound eXchange) es un convertidor de formato de archivo de sonido multiplataforma. SoX puede convertir entre muchos formatos de sonido digitalizados diferentes y realizar funciones simples de manipulación de sonido, incluidos los efectos de sonido. Puede combinar múltiples fuentes de entrada y sintetizar audio y actuar como reproductor de audio de uso general o una grabadora de audio multipista.   


A continuación veremos cómo instalarlo en Centos 7:

Para comenzar con el procedimiento de instalación de SoX, descargue el repositorio requerido usando el comando wget seguido del enlace de descarga.

```
wget http://repository.it4i.cz/mirrors/repoforge/redhat/el6/en/x86_64/rpmforge/RPMS/rpmforge-release-0.5.3-1.el6.rf.x86_64. rpm
```


Después de descargar el paquete, debemos instalarlo con el siguiente comando: 

```
rpm -ivh rpmforge-release-0.5.3-1.el6.rf.x86_64.rpm  
```

A continuación, instale las dependencias necesarias para que Sox se ejecute. Para ello, ejecutamos el comando yum install seguido de las dependencias:  

```
yum install gcc-c ++ libmad libmad-devel libid3tag libid3tag-devel lame-devel flac-devel libvorbis-devel
```

Descargue el último paquete de SoX estable utilizando el comando wget seguido del enlace de descarga:

```
wget https://nchc.dl.sourceforge.net/project/sox/sox/14.4.2/sox-14.4.2.tar.gz
```

Extraemos el paquete descargado ejecutando el comando tar:  

```
tar -xvzf sox-14.4.2.tar.gz
```  

Ahora debemos ir al directorio SoX y ejecutar el siguiente script para configurar el SoX en el sistema de destino:  

```
cd sox-14.4.2
./configure 
```

El proceso de configuración ha finalizado, ahora debemos ejecutar el comando make -s en la terminal:  

```
make -s 
```

Por último, ejecutamos el siguiente comando:  

```
make install
```




 









<!-- ![Texto alternativo](img/favicon.png) -->
