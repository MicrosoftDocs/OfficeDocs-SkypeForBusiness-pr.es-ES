---
title: Implementación de un alias y un puerto no estándar de SQL Server en Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35365cbd43aa3bea9afe5cdd036bd3834fae5037
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>Implementación de un alias y un puerto no estándar de SQL Server en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-09-16_

Microsoft Lync Server 2013 admite el uso de un puerto y un alias no estándar en SQL Server. El uso de un puerto no estándar de SQL Server y un alias aumenta la seguridad y crea un entorno más flexible para la implementación de Lync. Estos pasos son solo un paso para proteger correctamente el entorno de Lync Server 2013. Hay que seguir pasos adicionales para reducir la superficie de ataque de una implementación de 2013 de Lync Server.

En el siguiente artículo se describen los pasos necesarios para configurar un puerto no estándar y un alias de SQL Server en Lync Server 2013.

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>Implementar un puerto y alias no estándar de SQL Server en Lync Server 2013

El generador de topología de Lync Server 2013 admite el uso de un alias de SQL Server como nombre de dominio completo (FQDN) en lugar del FQDN real de SQL Server al configurar Lync Server 2013. Esto permite que el FQDN real de SQL Server esté oculto para cualquier atacante malintencionado. Además, el uso de un puerto no estándar oculta el puerto real de cualquier atacante que pudiera intentar atacar la base de datos en el puerto estándar 1433, tal como se muestra en la siguiente ilustración.

![Un pirata informático no sabe que el número de puerto es atacado.] (images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Un pirata informático no sabe que el número de puerto es atacado.")

Para tener éxito al determinar el puerto que usa Lync Server 2013 para comunicarse con SQL Server, el atacante necesita examinar todos los puertos para obtener la información del puerto. Una exploración de puertos por parte de un atacante aumenta las probabilidades de que la seguridad pueda detectar y detener la instrucción. Además de agregar mayor seguridad con un puerto no estándar, también puede usar un alias de SQL Server para proporcionar flexibilidad a la implementación. Esto es útil para reducir los cambios de configuración en situaciones en las que se requiere un cambio de nombre de SQL Server.

<div>


> [!NOTE]  
> SQL Server proporciona dos métodos de tolerancia a errores (clústeres de conmutación por error y reflejos). Los métodos de tolerancia a errores de SQL Server se admiten con un puerto no estándar y un alias de SQL Server con Lync Server 2013. Si el back-end de SQL Server utilizado por el grupo está en una configuración duplicada, el servicio explorador SQL de los servidores back-end de SQL Server debe estar ejecutándose para que los servidores de aplicaciones para el usuario se conecten a la base de datos reflejada cuando las bases de datos se conmutan por error a la SQL duplicada Servidores.



</div>

Al configurar la conectividad de base de datos de SQL Server desde el generador de topología, o al usar el cmdlet install-CsDatabase, no es posible definir de forma explícita un número de puerto no estándar de SQL Server y asociarlo a una instancia de SQL. Para establecer un puerto no estándar, tendrá que usar las utilidades de SQL Server y de Windows Server.

Para configurar un puerto y un alias no estándar de SQL Server para usar con Lync Server 2013, tendrá que completar tres pasos principales. Estos pasos son los siguientes:

  - Confirme que Lync Server 2013 tiene las actualizaciones más recientes aplicadas.

  - Configure el puerto y el alias no estándar de SQL Server.

  - Configure Lync Server 2013 con el alias de SQL Server con el generador de topología.

  - Publique la topología y Compruebe la base de datos.

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>Confirmar que Lync Server 2013 tiene las actualizaciones más recientes aplicadas

Es importante mantener Lync Server 2013 actualizado. Para consultar las actualizaciones más recientes e información sobre cómo aplicarlas, consulte [actualizaciones para Lync Server 2013](http://support.microsoft.com/kb/2809243).

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>Configurar el puerto y el alias no estándar de SQL Server

El puerto y el alias no estándar de SQL Server se deben configurar en la instancia de la base de datos para que se pueda hacer referencia a ellos desde el generador de topología de Lync Server 2013. Para configurar un puerto y un alias no estándar de SQL Server, tendrá que completar tres pasos principales. Estos pasos son los siguientes:

  - Cambie los valores predeterminados de los protocolos TCP/IP.

  - Crear y configurar un alias de SQL Server.

  - Crear un registro de recursos de nombre canónico (CNAME) del sistema de nombres de dominio (DNS).

**Modificar los valores predeterminados de los protocolos TCP/IP**

1.  Seleccione **Inicio**y elija **Administrador de configuración de SQL Server**, como se muestra en la siguiente ilustración.
    
    ![El icono de SQL Server Management Studio] (images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "El icono de SQL Server Management Studio")

2.  En el panel de navegación, elija expandir la **instancia de SQL Server**, expanda la **configuración de red de SQL Server**y elija **protocolos para\>el nombre de \<instancia**, como se muestra en la siguiente ilustración.
    
    ![Ir a propiedades de TCP/IP] (images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Ir a propiedades de TCP/IP")

3.  En el panel derecho, haga clic con el botón derecho en **TCP/IP**y seleccione **propiedades**. Se muestra el cuadro de diálogo Propiedades de TCP/IP.

4.  Seleccione la ficha **direcciones IP** . La ficha direcciones IP muestra todas las direcciones IP activas en el servidor. Están en el formato IP1, IP2, hasta IPAll, tal y como se muestra en la siguiente ilustración.
    
    ![Abra propiedades de TCP/IP.] (images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Abra propiedades de TCP/IP.")

5.  Borre el campo **puertos dinámicos TCP** para todas las direcciones IP. Si el campo contiene un carácter cero, significa que SQL Server está escuchando en puertos dinámicos. Asegúrese de que estos campos están desactivados y no contienen un cero.

6.  En la dirección IP que usará Lync Server para conectarse a la base de datos, asegúrese de que la **opción habilitada** está establecida en **sí**, tal y como se muestra en la siguiente ilustración.
    
    ![Establezca la opción habilitada como sí para la dirección IP correcta.] (images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Establezca la opción habilitada como sí para la dirección IP correcta.")

7.  En la sección **IPAll** de la parte inferior del cuadro de diálogo, escriba el puerto deseado en el campo **puerto TCP** , como se muestra en la siguiente ilustración. En este ejemplo, usamos el puerto 50062, pero puede usar cualquier puerto entre 49152 y 65535. Estos son los puertos asignados a uso dinámico y privado, y esto garantiza que no entrará en conflicto con otros puertos que se usan en la implementación de Lync Server 2013.
    
    ![Establezca puerto en la sección IPAll.] (images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Establezca puerto en la sección IPAll.")

8.  Elija **Aceptar** para salir del cuadro de diálogo Propiedades de TCP/IP.

9.  Para reiniciar la instancia de SQL Server, seleccione **servicios de SQL** Server en el panel izquierdo del administrador de configuración de SQL Server. A continuación, haga clic con el botón secundario en **nombre \<\> de instancia de SQL Server** en el panel derecho y seleccione **reiniciar**, como se muestra en la siguiente ilustración.
    
    ![Restablezca el servicio SQL Server para la instancia.] (images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Restablezca el servicio SQL Server para la instancia.")

<div>


> [!IMPORTANT]  
> Asegúrate de actualizar la configuración del firewall para que quepa en el nuevo puerto de SQL Server.



</div>

**Crear y configurar un alias de SQL Server**

1.  Seleccione **Inicio**y elija **Administrador de configuración de SQL Server**, como se muestra en la siguiente ilustración.
    
    ![El icono de SQL Server Management Studio] (images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "El icono de SQL Server Management Studio")

2.  En el panel izquierdo, elija expandir la **instancia de SQL Server**, seleccione para expandir la configuración de la ** \<versión\> de SQL Native Client**y, a continuación, elija **alias**, como se muestra en la siguiente ilustración.
    
    ![Alias en el administrador de configuración de SQL Server.] (images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Alias en el administrador de configuración de SQL Server.")

3.  Haga clic con el botón derecho en **alias**y seleccione **nuevo alias...**.

4.  Escriba el **nombre de alias**, el **número de Puerto**, el **Protocolo**y el **servidor**, tal y como se muestra en la siguiente ilustración.
    
    ![Crear un nuevo alias] (images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Crear un nuevo alias")
    
    <div>
    

    > [!CAUTION]  
    > Asegúrese de introducir el mismo puerto no estándar que usó en el paso anterior, ya que es el puerto en el que se escuchará SQL Server. Si un alias configurado se está conectando a un FQDN o instancia incorrecto de SQL Server, deshabilite y vuelva a habilitar el protocolo de red asociado. De este modo, se borrará la información de conexión almacenada en la memoria caché y el cliente se conectará correctamente.

    
    </div>

**Crear un registro de recursos CNAME de DNS**

1.  Inicie sesión en el equipo que administra DNS.

2.  Seleccione **Inicio**y elija **Administrador del servidor**, como se muestra en la siguiente ilustración.
    
    ![Abrir el administrador del servidor] (images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Abrir el administrador del servidor")

3.  Seleccione el menú desplegable **herramientas** y, a continuación, seleccione **DNS**, como se muestra en la siguiente ilustración.
    
    ![Abrir DNS desde el administrador del servidor.] (images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Abrir DNS desde el administrador del servidor.")

4.  En el panel de la izquierda, expanda el nodo nombre del servidor, expanda el nodo zonas de búsqueda directa y elija el dominio correspondiente.

5.  Haga clic con el botón derecho en el dominio y seleccione **nuevo alias (CNAME)...**, como se muestra en la siguiente ilustración.
    
    ![Selección de la opción para crear un nuevo alias CNAME] (images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selección de la opción para crear un nuevo alias CNAME")

6.  Escriba el **nombre de alias** y el **FQDN de SQL Server**, como se muestra en la siguiente ilustración.
    
    ![Rellenando el cuadro de diálogo nuevo alias CNAME.] (images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Rellenando el cuadro de diálogo nuevo alias CNAME.")

7.  Elija **Aceptar** para guardar el CNAME y verlo en el administrador de DNS.

</div>

<div>

## <a name="validate-database-connectivity"></a>Validar la conectividad de la base de datos

Hay varias formas diferentes de asegurarse de que funciona. Desea asegurarse de que la base de datos de SQL Server está escuchando en el puerto especificado usando el alias. Una comprobación rápida se puede completar con los comandos **netstat** y **telnet** .

<div>


> [!NOTE]  
> El cliente Telnet es una característica que se incluye con Windows Server, pero que debe instalarse. Para instalar una característica de Windows Server, abra el administrador del servidor y seleccione Agregar roles y características en el menú administrar.



</div>

**Usar netstat y Telnet para comprobar la conectividad de la base de datos**

1.  Seleccione **Inicio**y escriba **cmd** para abrir un símbolo del sistema.

2.  Escriba **netstat-a-f**y confirme que SQL Server se está ejecutando con el puerto correcto, tal y como se muestra en la siguiente ilustración.
    
    ![Uso de netstat para comprobar el puerto.] (images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Uso de netstat para comprobar el puerto.")

3.  Escriba **Puerto \< \# de nombre\> \<de alias de Telnet** para confirmar la conexión a la instancia de SQL Server. Si la conexión se realiza correctamente, Telnet se conectará y no se producirá un error. Esto muestra que la instancia de SQL Server está escuchando en el puerto correcto con el alias correcto. Si hay un problema al conectarse a la base de datos de SQL Server, entonces Telnet muestra un error que indica que no se puede establecer la conexión. Ahora que ha verificado la conectividad de la base de datos en el servidor de base de datos, puede hacer lo mismo desde Lync Server (a través de la red) y asegurarse de que no haya firewalls bloqueando el acceso durante el proceso.

</div>

<div>

## <a name="conclusion"></a>Conclusión

Una vez que el alias de SQL Server se ha configurado, puede usarlo para crear una topología de Lync Server 2013 en la herramienta Generador de topología. Para obtener más información acerca de las topologías, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for Security in Lync Server 2013](lync-server-2013-planning-for-security.md)  
[Definición y configuración de la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md)  
[Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

