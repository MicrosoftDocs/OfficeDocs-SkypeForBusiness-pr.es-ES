---
title: "Implementación de un alias y un puerto no estándar de SQL Server en Lync Server 2013"
TOCTitle: "Dépl. d’un port non standard et d’un alias SQL Server dans Lync Server 2013"
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634520
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementación de un alias y un puerto no estándar de SQL Server en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Microsoft Lync Server 2013 admite el uso de un alias y un puerto no estándar en SQL Server. El uso de un alias y un puerto no estándar de SQL Server aumenta la seguridad y crea un ambiente más flexible para la implementación de Lync. Estos pasos solo son un único paso de asegurar correctamente su entorno de Lync Server 2013. Deben tomarse medidas adicionales para reducir la superficie de ataque de una implementación de Lync Server 2013.

En el siguiente artículo se describen los pasos necesarios para configurar un alias y un puerto no estándar de SQL Server en Lync Server 2013.

## Implementación de un alias y un puerto no estándar de SQL Server en Lync Server 2013

Lync Server 2013Generador de topologías admite el uso de un alias de SQL Server como el nombre de dominio completo (FQDN) en vez del FQDN real de SQL Server al configurar Lync Server 2013. Esto permite que el real FQDN de SQL Server se oculte de cualquier atacante malintencionado. Además, el uso de un puerto no estándar oscurece el puerto real de cualquier intento de un atacante de atacar la base de datos en el puerto estándar 1433, como se muestra en la siguiente ilustración.

![Los atacantes no saben el número de puerto al que atacar.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Los atacantes no saben el número de puerto al que atacar.")

Para tener éxito a la hora de determinar el puerto que usa Lync Server 2013 para comunicarse con SQL Server, el atacante tendría que examinar todos los puertos para obtener la información del mismo. Un examen de puertos por parte de un atacante aumenta las posibilidades de que la seguridad pueda detectar y detener la instrucción. Además de agregar mayor seguridad con un puerto no estándar, también puede utilizar un alias de SQL Server para proporcionar flexibilidad en la implementación. Esto es valioso para reducir los cambios de configuración en situaciones donde se requiere un cambio de nombre de SQL Server.


> [!NOTE]
> SQL Server proporciona dos métodos de tolerancia a errores (clúster de conmutación por error y creación de reflejo). Ambos métodos de tolerancia a errores de SQL Server se admiten utilizando un alias y un puerto no estándar de SQL Server con Lync Server 2013.



Al configurar la conectividad de base de datos de SQL Server desde dentro de una Generador de topologías o al usar el cmdlet Install-CsDatabase, no es posible definir explícitamente un número de puerto no estándar de SQL Server y asociarlo con una instancia SQL. Para configurar un puerto no estándar, necesitará usar utilidades de SQL Server y Windows Server.

Para configurar un alias y un puerto no estándar de SQL Server para su uso con Lync Server 2013, necesitará completar tres pasos principales. Estos pasos son:

  - Confirmar que Lync Server 2013 tiene aplicadas las últimas actualizaciones.

  - Configurar el alias y el puerto no estándar de SQL Server.

  - Configurar Lync Server 2013 con el alias de SQL Server con la Generador de topologías.

  - Publicar la topología y comprobar la base de datos.

## Confirmar que Lync Server 2013 tiene aplicadas las últimas actualizaciones

Es importante mantener Lync Server 2013 actualizado. Para comprobar las actualizaciones más recientes e información sobre la manera de aplicarlas, vea [Actualizaciones para Lync Server 2013](http://support.microsoft.com/kb/2809243).

## Configurar el alias y el puerto no estándar de SQL Server

El alias y el puerto no estándar de SQL Server deben configurarse en la instancia de base de datos antes de que se puedan referenciar desde Lync Server 2013Generador de topologías. Para configurar un alias y un puerto no estándar de SQL Server, tendrá que completar tres pasos principales. Estos pasos son:

  - Cambiar los valores predeterminados del protocolo TCP/IP.

  - Crear y configurar un alias de SQL Server.

  - Crear un registro de recursos del nombre canónico (CNAME) del sistema de nombres de dominio (DNS) .

**Modificar los valores predeterminados del protocolo TCP/IP**

1.  Seleccione **Inicio** y **Administrador de configuración de SQL Server**, como se muestra en la siguiente ilustración.
    
    ![Icono de SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icono de SQL Server Management Studio")

2.  En el panel de navegación, expanda la **instancia de SQL Server**, expanda **Configuración de red de SQL Server** y seleccione **Protocolos de \<nombre de instancia\>**, como se muestra en la siguiente ilustración.
    
    ![Propiedades de Navegar a TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Propiedades de Navegar a TCP/IP")

3.  En el panel de la derecha, haga clic con el botón secundario en **TCP/IP** y seleccione **Propiedades**. Se muestra el cuadro de diálogo Propiedades de TCP/IP.

4.  Seleccione la pestaña **Direcciones IP**. La pestaña Direcciones IP muestra todas las direcciones IP activas en el servidor en el formato IP1, IP2, hasta IPAll, como se muestra en la siguiente ilustración.
    
    ![Propiedades de Abrir TCP/IP.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Propiedades de Abrir TCP/IP.")

5.  Borre el campo **Puertos dinámicos TCP** de todas las direcciones IP. Si el campo contiene un carácter cero, esto quiere decir que SQL Server está escuchando en los puertos dinámicos. Asegúrese de que estos campos están borrados y que no contienen un cero.

6.  En la dirección IP que utilizará Lync Server para conectarse a la base de datos, asegúrese de **habilitado** está establecido en **Sí**, como se muestra en la siguiente ilustración.
    
    ![Establece habilitado en Sí para la IP correcta.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Establece habilitado en Sí para la IP correcta.")

7.  En la sección **IPAll**, en la parte inferior del cuadro de diálogo, introduzca el puerto deseado en el campo **Puerto TCP**, como se muestra en la siguiente ilustración. En este ejemplo, usamos el puerto 50062, pero puede utilizar cualquier puerto entre 49152 y 65535. Son los puertos asignados para uso dinámico y privado y así se asegura de que que no entrarán en conflicto con otros puertos que se utiliza en la implementación de Lync Server 2013.
    
    ![Establece el puerto en la sección IPAII.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Establece el puerto en la sección IPAII.")

8.  Seleccione **Aceptar** para salir del cuadro de diálogo Propiedades de TCP/IP.

9.  Para reiniciar la instancia de SQL Server, seleccione **Servicios de SQL Server** en el panel izquierdo de Administrador de configuración de SQL Server. Luego haga clic con el botón secundario en **\<nombre de instancia\> de SQL Server** en el panel derecho y seleccione **Reiniciar**, como se muestra en la siguiente ilustración.
    
    ![Restablecer el servicio de SQL Server para la instancia.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Restablecer el servicio de SQL Server para la instancia.")

> [!IMPORTANT]  
> Asegúrese de actualizar la configuración de su firewall para adaptarla al nuevo puerto de SQL Server.



**Crear y configurar un alias de SQL Server**

1.  Seleccione **Inicio** y **Administrador de configuración de SQL Server**, como se muestra en la siguiente ilustración.
    
    ![Icono de SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icono de SQL Server Management Studio")

2.  En el panel izquierdo, expanda la **instancia de SQL Server**, expanda **Configuración SQL Native Client \<versión\>** y luego seleccione **Alias**, como se muestra en la siguiente ilustración.
    
    ![Alias de Administrador de configuración de SQL Server.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Alias de Administrador de configuración de SQL Server.")

3.  Haga clic con el botón secundario en **Aliases** y seleccione **Alias nuevo…**.

4.  Introduzca el **Nombre de alias**, **Número de puerto**, **Protocolo** y **Servidor**, como se muestra en la siguiente ilustración.
    
    ![Creando un alias nuevo](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creando un alias nuevo")
    
    > [!CAUTION]  
    > Asegúrese de introducir el mismo puerto no estándar que usó en el paso anterior ya que SQL Server escuchará en este puerto. Si un alias configurado se conecta al FQDN o a la instancia del SQL Server erróneos, deshabilite y luego vuelva a habilitar el protocolo de red asociado. Al hacer esto se borra cualquier información de conexión de la memoria caché y permite al cliente conectarse correctamente.
    


**Crear un registro de recursos del CNAME del DNS**

1.  Inicie sesión en el equipo que administra DNS.

2.  Seleccione **Inicio** y **Administrador de servidor**, como se muestra en la siguiente ilustración.
    
    ![Abriendo Administrador de servidores](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Abriendo Administrador de servidores")

3.  Seleccione el desplegable **Herramientas** y luego **DNS**, como se muestra en la siguiente ilustración.
    
    ![Abriendo DNS desde el Administrador de servidores.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Abriendo DNS desde el Administrador de servidores.")

4.  En el panel izquierdo, expanda el nodo del nombre de servidor, expanda el nodo Zonas de búsqueda directa y seleccione el dominio correspondiente.

5.  Haga clic con el botón secundario en el dominio y seleccione **Alias nuevo (CNAME)…**, como se muestra en la siguiente ilustración.
    
    ![Seleccionando opción para crear un nuevo CNAME de alias](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Seleccionando opción para crear un nuevo CNAME de alias")

6.  Introduzca el **Nombre de alias** y el **FQDN de SQL Server**, como se muestra en la siguiente ilustración.
    
    ![Cuadro de diálogo Rellenando el nuevo CNAME de alias.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Cuadro de diálogo Rellenando el nuevo CNAME de alias.")

7.  Seleccione **Aceptar** para guardar el CNAME y verlo en el Administrador de DNS.

## Validar la conectividad de base de datos

Hay muchas maneras diferentes para asegurarse de que funciona. Quiere asegurarse de que la base de datos SQL Server está escuchando en el puerto especificado utilizando el alias. Una comprobación rápida puede ser realizada con los comandos **netstat** y **telnet**.


> [!NOTE]
> Cliente Telnet es una característica que viene con Windows Server, pero que debe instalarse. Una característica de Windows Server se puede instalar abriendo el Administrador de servidores y seleccionando Agregar roles y características en el menú Administrar.



**Usar netstat y telnet para comprobar la conectividad de base de datos**

1.  Seleccione **Inicio** y escriba **cmd** para abrir un símbolo del sistema.

2.  Escriba **netstat -a -f** y confirme que SQL Server se está ejecutando con el puerto correcto, como se muestra en la siguiente ilustración.
    
    ![Usando netstat para comprobar el puerto.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Usando netstat para comprobar el puerto.")

3.  Escriba **telnet \<nombre de alias\> \<número de puerto \>** para confirmar la conexión a la instancia de SQL Server. Si la conexión es correcta, telnet se conectará y no debería ver ningún error. Esto demuestra que la instancia de SQL Server está escuchando en el puerto correcto con el alias correcto. Si hay un problema de conexión a la base de datos de SQL Server, entonces telnet muestra un error que indica que no se puede realizar la conexión. Ahora que ha comprobado la conectividad de base de datos en el servidor de base de datos, puede hacer lo mismo desde Lync Server (a través de la red) y asegurarse de que no hay ningún firewall que bloquee el acceso en toda la ruta.

## Conclusión

Una vez configurado el alias de SQL Server, puede utilizarlo para crear una topología de Lync Server 2013 en la herramienta Generador de topologías . Para más información sobre topologías, consulte [Definición y configuración de la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md)Supported Lync Server 2013 Preview Topologies.

## Vea también

#### Conceptos

[Microsoft Lync Server 2013](microsoft-lync-server-2013.md)  

#### Otros recursos

[Planeación de seguridad en Lync Server 2013](lync-server-2013-planning-for-security.md)  
[Definición y configuración de la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md)  
[Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md)

