# AZURE VIRTUAL NETWORK

![Virtual Network](Imagenes\vitualNetwork.png)

**Network: proporciona servicios de red que permiten conectar los recursos con el mundo exterior**

- **modelo de servicio:** IaaS
- **Funcion:** permite que los recursos de azure se comuniquen.
- **Funcion:** Permite enrutamiento de trafico de red.
- **Funcion:** Permite el filtrado de trafico de red.
- **Cuando usar:** Conectar maquinas virtuales.

-----------------------------------------------------------------------

#### Pasos para conectar dos Redes Virtuales

1.- Abrimos el [Portal de Azure](https://portal.azure.com/)

2.- Creamos un nuevo grupo de recursos
revisar y crear, luego le damos crear.

 ![Grupo de Recursos](Imagenes\groupresorurces.JPG)


3.- AHora creamos la red Virtual para que asi la maquina virtual quede dentro de la red.

![Create Virtual Network](Imagenes\redvirtual.JPG)


4.- Una ves que entremos a redes virtuales, le damos crear para empezar a configurarla.

5.- Aca le ponemos un nombre y seleccionamos el nuevo grupo de recursos que creamos.

6.- Nos vamos a la pestaña que dice Direccion IP para crear una subred.

7.- para crear la sub red, debemos eliminar la que se crea por default para que podamos crear una nosotros.

8.- Ahora le damos en revisar y crear, para que asi le demos crear.

![VirtualNetwork1](Imagenes\virtualnetwork1.JPG)

9.- Vamos a crear otra red virtual, con el mismo grupo de recursos, pero otro nombre.

10.- En la pestaña de direccion virtual eliminamos la sub red y creamos una sub red nueva con la diferencia que ahora el Ip empezara el 3 numero con 1.Por ejemplo: **1.0.1.0/24**

11.- Ahora procedemos a revisar y crear, para crear la segunda red virtual.

![VirtualNetwork2](Imagenes\virtualnetwork2.JPG)


**nota: Por que nos creamos otra? por que en mi suscripcion ya existe una red que esta ocuoando ese lugar.**

12.- ahora nos vamos a nuestra redvirtual1.

13.- Nos iremos a la parte izquierda donde dice emparejamientos.

14.- Aca vamos a conectar las redes virtuales.

**nota: Para ver el funcionamiento, vamos a crear dos maquinas virtuales**

![MaquinaVirtual](Imagenes\machine.PNG)

15.- Nos vamos a crear las maquinas virtuales que seran de Linux **(ubuntu server 20.04)**.

16.- Le damos un Usuario y una contraseña a la maquina Virtual.

17.- En inbound ports, checamos que este seleccionado el SSCH

18.- ahora en la parte de **redes** en la maquina virtual, debemos porner la redvirtual 1 **(pero debemos asegurarnos que las redes y las maquinas esten en la misma region)**

![Network Machine](Imagenes\networkmachine.JPG)

19.- A continuacion le damos en revisar y crear, dejemos que se cree esa maquina.

20.- Creamos la segunda maquina con los mismos pasos, la diferencia es que en la seccion de redes, debemos buscar la red virtual 2 y la sub net 2.

21.- Ahora nos vamos a la maquina virtual 1 y nos vamos a la seccion de conectar SSH, estando ahi debemos darle click al Cloud Shell donde usaremos codigos para controlar Azure.

![ssh](Imagenes\ssh.JPG)

22.- copiamos el comando de la maquia virtual

![Comando de SSH](Imagenes\shellssh.JPG)

23.- le damoc click al cloud shell y le damos clik donde dice crear almacenamiento darle click a nuestro almacenamiento

24.- ahora una ves que cargue pondremos el comando "ssh y pegamos el comando que nos habian dado"
![bash](Imagenes\bash.JPG)

25.- una ves que lo hagamos, nos dira que si queremos continuar, a lo que le diremos que "yes"

![yes](Imagenes\yes.JPG)

26.- Una ves que cargue todo ese proceso, cuando en nuetsro usuario aparzca **@ y el nombre de la maquina virtual que le dimos**, significa que ya estamos conectados

![Usuario Conectado](Imagenes\usuarioubuntu.JPG)


27.- si quieres hacer una prueba para ver si estas conectado, deberas pondras el comando **sudo apt-get moo** y te aparecera una vaquita

![moo](Imagenes\moo.JPG)

28.- Para conectar las otra maquina virtual, debemor ir a nuestra red virtual 1 y a la seccion que dice Emparejamientos.

![Emparejar](Imagenes\pearing.JPG)

29.- creamos un emparejamiento, dandole un nombre y nombre al vinculo.

![Vinculo0](Imagenes\linknamepeering.JPG)

30.- seleccionamos la red virtual que queremos conectar.

![pearing](Imagenes\virtualconection.JPG)

31.- Le damos un nombre a este emparejamiento remoto.

**NOTA: De preferencia, lo que pusiste al principio pero al revez.

![name pearing](Imagenes\remotepeering.JPG)

32.- Volvemos al Bash y lo que haremos es poner el comando **ping y el ID de la segunda red virtual** nos desplegara varios datos, lo que significara que estara conectada.

![Conectar Segunda red Virtual](Imagenes\porfinconectado.JPG)


----------------------------------------------------------------------------------
