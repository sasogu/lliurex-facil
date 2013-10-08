La Guia NO OFICIAL del Modelo de Aula en LliureX 13.06 _Pandora_
================================================================

En el modelo de Aula LliureX para la versión 13.06 se han cambiado muchas cosas y se han realizado muchos cambios que tienen que ver con el montaje de las unidades de red. Esto ha tenido que ver con el cambio a Samba y con la implementación del modelo de centro inteligente. 

Usuarios de Red
----------------

Los usuarios de red dentro del modelo de aula siguen estando en el servidor LDAP. En el caso de que se esté montando un modelo de centro inteligente, los LDAP de los distintos servidores del centro están sincronizados, pudiendo efectuar sobre ellos cualquier operación (siempre que todo funcione como _$DEITY_ manda) con el **Llum**[^1]. En el caso de que el servidor de centro este caido, cosa que no es en absoluto recomendable, tan solo se podrán efectuar operaciones de lectura sobre el LDAP.

[^1]: El uso del **Llum** sin duda requiere de un capítulo aparte ^_^.

En versiones anteriores de LliureX, las carpetas personales de los usuarios (_aka HOMES_), estaban montadas por *NFS* desde el servidor. Se montaba todo _/net_ en los clientes, teniendo disponible para todos los usuarios el acceso a las diferentes carpetas:

* /net/home/students/alu01
* /net/home/students/alu02
* /net/home/students/amargar
* /net/home/teachers/profe01

¿Como se controlaba esto? Pues muy sencillo, se usaba Kerberos y ACLs (_listas de control de acceso_) para impedir que otros usuarios que no fueran los propietarios de los ficheros acceder a los mismos. 

Pero ahora, en la era de **Samba**, este mecanismo no se podía implementar, ya que cuando se monta algo por **Samba** lo que ocurre es que el usuario que escribe en esas carpetas compartidas es el que lo monta, así que no se podía usar un *mecanismo general* de montaje para todos los usuarios. ¿Qué es lo que se ha implementado?...sigan leyendo...


PAM y puntos de montaje
-----------------------

Cuando un usuario hace login en una máquina, ya sea via *SSH* o mediante el gestor gráfico *Lightdm* (*LTSP merece una mención aparte*[^2]), se ejecutan una serie de scripts que realizan funciones básicas:

[^2]: Lo veremos en próximos capítulos.

* Creación del $HOME : _pam_mkhomedir_
* Obtención del entorno para el usuario : _pam_getenv_
* Y otros muchos...

Lo que se hace en uno de estos pasos es montar las carpetas del usuario en :

	/run/_nombre-usuario_/ 

desde el servidor del aula. ¿Y donde está esa carpeta en el servidor? Pues en :

	/net/server-sync/home/students/nombre-usuario/


Pero esto no es muy _Human readable_, ni cómodo para el usuario, así que más adelante en el proceso de login, en este caso los scripts de **Lightdm** se monta con la opción _--bind_ las carpetas desde _/run/_ a _/home/nombre-usuario/_ y no se monta todo el _$HOME_ si no tan solo las siguientes carpetas:

* Para los alumnos:
	* Desktop
	* Documents
	* Share
* Para los profesores, ademas de las anteriores se montan tambien:
	* alum (que equivale a la carpeta del servidor /net/server-sync/home/students que sirve para acceder a las carpetas de los alumnos)
	* Share_teachers ( Carpeta compartida para los profesores que no tendran acceso los alumnos)

Sin embargo, para tener en cuenta las preferencias del idioma de cada usuario, esas carpetas se van cambiando de nombre y se crean los enlaces como toca. 

¿Problemas?
-----------

Por supuesto que los hay, pero se está trabajando en ellos, por ejemplo, los enlaces a las carpetas Desktop (_o Escritorio, Escriptori,..._) no se crean hasta que el usuario no inicia sesión mediante la interfaz gráfica. Así que copiarle algo a los alumnos es mucho más práctico desde el servidor en el sistema de ficheros local. 

Ejemplo:

_Quiero copiarle el fichero tareas.odt al alumno fermargar, y quiero dejarselo en su escritorio...¿Cómo lo hago?_

El orden de recomendacion para copiar un fichero seria:

1. Copio en el servidor el fichero tareas.odt a la carpeta alum/fermargar/Desktop de mi carpeta personal 
2. Copio en el servidor el fichero tareas.odt a la carpeta /run/**_mi_usuario_**/home/students/fermargar/Desktop
3. Copio en el servidor el fichero tareas.odt a la carpeta /net/server-sync/home/students/fermargar/Desktop/