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

![LliureX LTSP Image][lliurex-ltsp-images-management]

Como podemos observar, tan solo tenemos disponible el botón de **Install** de cada una de las imágenes, más adelante veremos las opciones avanzadas. Si pulsamos nos muestra la siguiente pantalla

![LliureX LTSP Image Prev][lliurex-ltsp-image-prev-creation]

Y ahora si pulsamos sobre el botón, nos vamos a por un buen café. Mientras que LliureX hace todo el trabajo duro.

![Un buen café][cafe]

![LliureX LTSP Image Creation Progress][lliurex-ltsp-image-creation-progress]

Una vez se ha creado la imágen (para lo cual se tomará más de media hora), ya podemos arrancar en el aula los clientes por red e iniciar sesión con los usuarios de red, tal y como lo haríamos si estuvieran instalados.

Este es el mensaje cuando acaba:



Habilitar/deshabilitar la instalación por red en el aula
--------------------------------------------------------

En el apartado de instalación por red, lo único que tenemos es un botón que nos permite habilitar (o deshabilitar) la instalación por red en el aula.

Esta instalación usará los paquetes del Mirror de LliureX que haya en el servidor, por lo que actualizarlo a la última versión *nunca está de más*, tal y como se explica (de nuevo) aquí: [LliureX Mirror](https://github.com/aberlanas/lliurex-facil/blob/master/src/lliurex-mirror/lliurex-mirror.md)

![LliureX LTSP network installation][lliurex-ltsp-network-install]


Lo que se ve si se arranca por red un cliente y se tiene la instalación por red habilitada en el servidor es lo siguiente:

[lliurex-ltsp-network-install-client-boot]

Y luego podemos elegir el tipo de instalación que queremos para la máquina

[lliurex-ltsp-network-install-client-boot-choose]

La instalación irá haciendonos las preguntas correspondientes. Tenemos un capítulo para esto aquí: [Instalación por red](https://github.com/aberlanas/lliurex-facil/blob/master/src/network-install/network-install.md)

<!-- imagenes -->

[lliurex-ltsp-menu]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_menu.png "LliureX LTSP"
[lliurex-ltsp-intro]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_intro.png "LliureX LTSP Intro"
[lliurex-ltsp-main-menu]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_main_menu.png "LliureX LTSP Main Menu"
[lliurex-ltsp-images-management]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_images_management.png "LliureX LTSP Main Menu"
[lliurex-ltsp-image-creation]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_image_creation.png "LliureX LTSP Image Creation"
[lliurex-ltsp-image-prev-creation]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_create_prev.png "LliureX LTSP Image Creation"
[lliurex-ltsp-image-creation-progress]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_image_creation_progress.png "LliureX LTSP image creation progress"
[lliurex-ltsp-network-install]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_network_install.png "LliureX LTSP network installation"
[lliurex-ltsp-network-install-client-boot]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_network_install_client_boot.png "LliureX LTSP network installation"
[lliurex-ltsp-network-install-client-boot-choose]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/lliurex-ltsp/lliurex_ltsp_network_install_client_boot_choose.png "LliureX LTSP network installation"

[cafe]: https://raw.github.com/aberlanas/lliurex-facil/master/imgs/miscelanea/cafe.jpg "Cafe"

