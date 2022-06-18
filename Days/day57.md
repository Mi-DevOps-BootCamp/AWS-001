Administrar servicios con systemctl


https://geekflare.com/es/manage-systemd-services-with-systemctl/

¿Cómo administrar los servicios de Systemd con Systemctl?


El administrador de sistemas y servicios predeterminado para la mayoría de las distribuciones de Linux ahora es systemd

El proceso de la systemd proceso reemplaza el SysV init. Se ejecuta como el primer proceso después del arranque del kernel y es responsable de llevar el host Linux al estado en el que se puede utilizar. Es responsable de iniciar y administrar los servicios, montar sistemas de archivos, administrar el hardware, generar el indicador de inicio de sesión y mucho más.

Un beneficio clave sobre SysV es que systemd inicia tantos servicios como sea posible en paralelo, acelerando así la proceso de inicio, y eso hace que aparezca la pantalla de inicio de sesión más rápido.


Unidades
Los elementos gestionados por systemd se denominan unidades. Los archivos de la unidad se encuentran en /lib/systemd/sistema.

Unidades de servicio
Para la gestión de servicios, las unidades de destino son unidades de servicio, que tienen archivos de unidad con un sufijo de .Servicio.

Gestión de servicios systemd
El comando para administrar las unidades systemd es systemctl.

Iniciar y detener servicios
Para iniciar un servicio systemd, use el comando systemctl start:

$ sudo systemctl start name.service
Puede dejar el sufijo .service. Por ejemplo, para iniciar el servidor apache en Ubuntu:

$ sudo systemctl start apache2
Para detener un servicio en ejecución:

$ sudo systemctl stop name.service

Entonces, para detener el servidor apache en Ubuntu:

$ sudo systemctl stop apache2
Servicios de reinicio y recarga
Para reiniciar un servicio en ejecución, use el comando de reinicio:

$ sudo systemctl restart name.service
Y donde se requiere el único archivo de configuración de recarga

$ sudo systemctl reload name.service
Habilitación y deshabilitación de servicios
Si desea que un servicio se inicie automáticamente al iniciar el sistema, use el comando enable:

$ sudo systemctl enable name.service

Para desactivar un servicio para que no se inicie en el inicio del sistema:

$ sudo systemctl disable name.service

La desactivación no detiene un servicio en ejecución.

Ver el estado del servicio

Para ver información sobre un servicio:

$ sudo systemctl status name.service
Esto le mostrará el estado del servicio y las primeras líneas del archivo de registro. Entonces, mientras se ejecuta el servicio, la salida de

sudo systemctl status apache2
is

apache2.service - The Apache HTTP Server
   Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)
  Drop-In: /lib/systemd/system/apache2.service.d
           └─apache2-systemd.conf
   Active: active (running) since Tue 2020-05-19 22:11:36 UTC; 4 days ago
  Process: 116002 ExecReload=/usr/sbin/apachectl graceful (code=exited, status=0/SUCCESS)
Main PID: 104165 (apache2)
    Tasks: 55 (limit: 1024)
   CGroup: /system.slice/apache2.service
           ├─104165 /usr/sbin/apache2 -k start
           ├─116006 /usr/sbin/apache2 -k start
           └─116007 /usr/sbin/apache2 -k start


May 19 22:11:36 ubuntu18 systemd[1]: Starting The Apache HTTP Server...
May 19 22:11:36 ubuntu18 systemd[1]: Started The Apache HTTP Server.
May 21 06:25:01 ubuntu18 systemd[1]: Reloading The Apache HTTP Server.
May 21 06:25:01 ubuntu18 systemd[1]: Reloaded The Apache HTTP Server.
May 22 06:25:01 ubuntu18 systemd[1]: Reloading The Apache HTTP Server.
Para comprobar si un servicio está activo:

$ sudo systemctl is-active name.service

Entonces, mientras se ejecuta el servicio apache2, el resultado del comando systemctl is-active es:

$ sudo systemctl is-active apache2
active
Para comprobar si un servicio está habilitado:

$ sudo systemctl is-enabled name.service.

Viewing System State


Todos los comandos que ha visto hasta ahora se utilizan para administrar un solo servicio. Cuando desee una descripción general del estado del sistema, utilice el siguiente conjunto de comandos:

Para ver todos los tipos de unidades

$ sudo systemctl -t help
Available unit types:
service
socket
target
device
mount
automount
swap
timer
path
slice
scope


Para enumerar todas las unidades instaladas, use list-unit-files

$ sudo systemctl list-unit-files
UNIT FILE                              STATE          
proc-sys-fs-binfmt_misc.automount      static         
-.mount                                generated      
boot-efi.mount                         generated      
dev-hugepages.mount                    static         
dev-mqueue.mount                       static         
mnt.mount                              generated      
proc-sys-fs-binfmt_misc.mount          static         
sys-fs-fuse-connections.mount          static         
sys-kernel-config.mount                static         
sys-kernel-debug.mount                 static         
acpid.path                             enabled        
apport-autoreport.path                 enabled        
systemd-ask-password-console.path      static         
systemd-ask-password-plymouth.path     static         
systemd-ask-password-wall.path         static         
session-161.scope                      transient      
accounts-daemon.service                enabled        
La salida tiene solo dos columnas Archivo de unidad y Estado. El estado generalmente será habilitado, deshabilitado, estático o enmascarado.

Estático: Esto significa que la unidad no se puede habilitar, realiza una acción única o es una dependencia de otra unidad y no se puede ejecutar por sí misma.

Enmascarado: Una unidad listada como enmascarada significa que es completamente inestable, ya que está vinculada a / dev / null. A esto se le llama enmascarar la unidad. Esto evita que el servicio se inicie, manual o automáticamente.

Lista de todos los servicios instalados

El comando systemctl list-unit-files con -t o –type service filter muestra solo el estado de los servicios instalados.

$ sudo systemctl list-unit-files -t service
UNIT FILE                              STATE    
accounts-daemon.service                enabled  
acpid.service                          disabled 
apache-htcacheclean.service            disabled 
apache-htcacheclean@.service           disabled 
apache2.service                        enabled  
apache2@.service                       disabled 
apparmor.service                       enabled  
apport-autoreport.service              static   
apport-forward@.service                static   
apport.service                         generated
apt-daily-upgrade.service              static   
apt-daily.service                      static   
atd.service                            enabled  
autovt@.service                        enabled  
blk-availability.service               enabled  
bootlogd.service                       masked   
bootlogs.service                       masked   


Para ver todas las unidades de servicio activas, use list-units con -t service filter

$ sudo systemctl list-units -t service


UNIT                                 LOAD   ACTIVE SUB     DESCRIPTION                             
  accounts-daemon.service              loaded active running Accounts Service                        
  apache2.service                      loaded active running The Apache HTTP Server                  
  apparmor.service                     loaded active exited  AppArmor initialization                 
  apport.service                       loaded active exited  LSB: automatic crash report generation  
  atd.service                          loaded active running Deferred execution scheduler            
  blk-availability.service             loaded active exited  Availability of block devices           
  cloud-config.service                 loaded active exited  Apply the settings specified in cloud-con
  cloud-final.service                  loaded active exited  Execute cloud user/final scripts        
  cloud-init-local.service             loaded active exited  Initial cloud-init job (pre-networking) 
  cloud-init.service                   loaded active exited  Initial cloud-init job (metadata service 
  console-setup.service                loaded active exited  Set console font and keymap             
  cron.service                         loaded active running Regular background program processing dae
  
  
  
La salida tiene las siguientes columnas:


UNIDAD: El nombre de la unidad de servicio systemd

CARGA: Muestra si la definición de la unidad se leyó y cargó correctamente

ACTIVE: Describe si la unidad está activa.

SUB: Estado de activación de bajo nivel de la unidad, que proporciona información más detallada sobre la unidad. Esto variará según el tipo de unidad.

DESCRIPCIÓN: Descripción de la unidad de servicio.

Conclusión
Espero que esto le dé una idea sobre el uso de systemctl para administrar servicios en Linux.







#
#
#
#
#

See you on [Day 58](day58.md)
