LliureX Y LTSP
==============


LliureX abandonó *TcOS* a favor de *LTSP* en la versión 13.06. Los motivos para este cambio son muchos pero entre ellos podríamos destacar:

* Falta de soporte en TcOS.
* Amplia comunidad LTSP.
* Tecnología más avanzada y optimizada.

LliureX LTSP en 60 Segundos
---------------------------

En el menú de *Administración de LliureX* hay una entrada que es *LliureX LTSP*.

![LliureX LTSP en el Menú][lliurex-ltsp-menu]

Cuando lo abrimos nos muestra la siguente pantalla:

![LliureX LTSP intro][lliurex-ltsp-intro]

El usuario que nos pide debe ser administrador de la máquina local (*la opción remota la comentaremos más adelante*), o el usuario **netadmin**

Este **netadmin** es el usuario al que le hemos puesto la contraseña al inicializar el servidor. Este es el _recomendado_ para la realización de las tareas de administración de aula.

Dentro de LliureX LTSP
----------------------

Una vez autenticados en LliureX LTSP lo que se nos muestra (_si tenemos el mirror creado_) es esto:

![LliureX LTSP Menu][lliurex-ltsp-main-menu]

Desde aquí podemos:

* Actualizar el mirror.
* Administrar el aula.
* Crear imágenes de LTSP para el aula.
* Habilitar/deshabilitar la instalación por red en el aula.

Vamos de uno en uno ahora

Actualizar el mirror
--------------------

Esto funciona exactamente como dice aquí: [LliureX Mirror](https://github.com/aberlanas/lliurex-facil/blob/master/src/lliurex-mirror/lliurex-mirror.md)


Administrar el aula
-------------------

Para explicar esto no valen 60 segundos...así que lo veremos más adelante ^_^


Crear imágenes de LTSP para el aula
-----------------------------------

Las imágenes de LTSP que se crean aquí serán los distintos *sabores* que se podrán arrancar para trabajar en el aula sin necesidad de tener los sistemas instalados. Esto es típicamente para los clientes ligeros (**thin-clients**) y para los equipos que por cualquier razón quisieramos arrancar en el aula sin usar su disco duro (*faenas de reparación,un portátil con virus,ect.*)

Se muestra una imágen como la siguiente:

![LliureX LTSP Image][lliurex-ltsp-image-creation]

Como podemos observar, tan solo tenemos disponible el botón de **Install** de cada una de las imágenes, más adelante veremos las opciones avanzadas. Si pulsamos nos muestra la siguiente pantalla

![LliureX LTSP Image Prev][lliurex-ltsp-image-prev-creation]



[lliurex-ltsp-menu]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_menu.png "LliureX LTSP"
[lliurex-ltsp-intro]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_intro.png "LliureX LTSP Intro"
[lliurex-ltsp-main-menu]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_main_menu.png "LliureX LTSP Main Menu"
[lliurex-ltsp-image-creation]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_image_creation.png "LliureX LTSP Image Creation"
[lliurex-ltsp-image-prev-creation]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_create_prev.png "LliureX LTSP Image Creation"
[lliurex-ltsp-image-creation-progress]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_image_creation_progress.png "LliureX LTSP image creation progress"
