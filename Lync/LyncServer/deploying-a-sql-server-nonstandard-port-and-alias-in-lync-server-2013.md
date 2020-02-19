---
title: Implementación de un puerto y alias no estándar de SQL Server en Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1134422c8c55a60858a9fd8c28be2e6ff159d48
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>Implementación de un puerto y alias no estándar de SQL Server en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-09-16_

Microsoft Lync Server 2013 admite el uso de un puerto y un alias no estándar en SQL Server. El uso de un puerto no estándar de SQL Server y un alias aumenta la seguridad y crea un entorno más flexible para la implementación de Lync. Estos pasos son un solo paso para proteger correctamente el entorno de Lync Server 2013. Se deben realizar pasos adicionales para reducir la superficie de ataque de una implementación de Lync Server 2013.

En el siguiente artículo se describen los pasos necesarios para configurar un puerto y un alias no estándar de SQL Server en Lync Server 2013.

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>Implementación de un puerto y alias no estándar de SQL Server en Lync Server 2013

El generador de topologías de Lync Server 2013 admite el uso de un alias de SQL Server como nombre de dominio completo (FQDN) en lugar del FQDN real de SQL Server al configurar Lync Server 2013. Esto permite que el FQDN real de SQL Server esté oculto para los intrusos malintencionados. Además, el uso de un puerto no estándar oculta el puerto real de cualquier atacante que intentara atacar la base de datos en el puerto estándar 1433, tal como se muestra en la siguiente figura.

![Un pirata informático no conoce el número de puerto que se va a atacar.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Un pirata informático no conoce el número de puerto que se va a atacar.")

Para poder determinar correctamente el puerto que Lync Server 2013 usa para comunicarse con SQL Server, el atacante debe analizar todos los puertos para obtener la información del puerto. Un examen de puertos por parte de un atacante aumenta las probabilidades de que la seguridad pueda detectar y detener la instrucción. Además de agregar mayor seguridad con un puerto no estándar, también puede usar un alias de SQL Server para proporcionar flexibilidad a la implementación. Esto es útil para reducir los cambios en la configuración en situaciones en las que se requiere un cambio de nombre de SQL Server.

<div>


> [!NOTE]  
> SQL Server proporciona dos métodos de tolerancia a errores (clústeres de conmutación por error y reflejos). Ambos métodos de tolerancia a errores de SQL Server se admiten con un puerto no estándar de SQL Server y un alias con Lync Server 2013. Si el back-end de SQL Server usado por el grupo está en una configuración reflejada, el servicio de explorador SQL de los servidores back-end de SQL Server debe ejecutarse para que los servidores front-end se conecten a la base de datos reflejada cuando las bases de datos se conmutan por error a la copia de SQL reflejada. Server.



</div>

Al configurar la conectividad de base de datos de SQL Server desde el generador de topologías o al usar el cmdlet install-CsDatabase, no es posible definir explícitamente un número de puerto no estándar de SQL Server y asociarlo con una instancia de SQL. Para establecer un puerto no estándar, deberá usar las utilidades de SQL Server y Windows Server.

Para configurar un puerto y un alias no estándar de SQL Server para su uso con Lync Server 2013, tendrá que completar tres pasos principales. Los pasos son:

  - Confirme que Lync Server 2013 tiene las actualizaciones más recientes aplicadas.

  - Configure el puerto y el alias no estándar de SQL Server.

  - Configure Lync Server 2013 con el alias de SQL Server mediante el generador de topologías.

  - Publique la topología y Compruebe la base de datos.

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>Confirmar que Lync Server 2013 tiene las actualizaciones más recientes aplicadas

Es importante mantener Lync Server 2013 al día. Para consultar las actualizaciones más recientes e información sobre cómo aplicarlas, consulte [actualizaciones para Lync Server 2013](https://support.microsoft.com/kb/2809243).

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>Configurar el puerto y el alias no estándar de SQL Server

El alias y el puerto no estándar de SQL Server se deben configurar en la instancia de la base de datos para que se pueda hacer referencia a él desde el generador de topologías de Lync Server 2013. Para configurar un puerto y un alias no estándar de SQL Server, tendrá que completar tres pasos principales. Estos pasos son los siguientes:

  - Cambie los valores predeterminados del protocolo TCP/IP.

  - Cree y configure un alias de SQL Server.

  - Cree un registro de recursos de nombre canónico (CNAME) del sistema de nombres de dominio (DNS).

**Modificación de los valores predeterminados del protocolo TCP/IP**

1.  Seleccione **Inicio**y elija **Administrador de configuración de SQL Server**, como se muestra en la ilustración siguiente.
    
    ![El icono de SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "El icono de SQL Server Management Studio")

2.  En el panel de navegación, expanda la **instancia de SQL Server**, expanda la opción **configuración de red de SQL Server**y elija **protocolos\>para nombre \<de instancia**, como se muestra en la siguiente ilustración.
    
    ![Ir a propiedades de TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Ir a propiedades de TCP/IP")

3.  En el panel derecho, haga clic con el botón secundario en **TCP/IP**y seleccione **propiedades**. Se muestra el cuadro de diálogo Propiedades de TCP/IP.

4.  Seleccione la pestaña **direcciones IP** . La pestaña direcciones IP muestra todas las direcciones IP activas en el servidor. Se encuentran en el formato IP1, IP2, hasta IPAll, como se muestra en la siguiente ilustración.
    
    ![Abra propiedades de TCP/IP.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Abra propiedades de TCP/IP.")

5.  Borre el campo **puertos dinámicos TCP** para todas las direcciones IP. Si el campo contiene un carácter cero, significa que SQL Server está escuchando en puertos dinámicos. Asegúrese de que estos campos se hayan borrado y no contengan un cero.

6.  Para la dirección IP que Lync Server usará para conectarse a la base de datos, asegúrese de que **Enabled** está establecido en **yes**, tal como se muestra en la figura siguiente.
    
    ![Establezca Enabled como sí para la dirección IP correcta.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Establezca Enabled como sí para la dirección IP correcta.")

7.  En la sección **IPAll** de la parte inferior del cuadro de diálogo, escriba el puerto deseado en el campo **puerto TCP** , tal como se muestra en la ilustración siguiente. En este ejemplo, usamos el puerto 50062, pero puede usar cualquier puerto entre 49152 y 65535. Estos son los puertos asignados al uso dinámico y privado, y esto garantiza que no entren en conflicto con otros puertos que se usan en la implementación de Lync Server 2013.
    
    ![Establecer puerto en la sección IPAll.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Establecer puerto en la sección IPAll.")

8.  Haga clic en **Aceptar** para salir del cuadro de diálogo Propiedades de TCP/IP.

9.  Reinicie la instancia de SQL Server seleccionando **servicios de SQL Server** en el panel izquierdo del administrador de configuración de SQL Server. A continuación, haga clic con el botón secundario en **nombre \<\> de instancia de SQL Server** en el panel derecho y seleccione **reiniciar**, como se muestra en la ilustración siguiente.
    
    ![Restablezca el servicio de SQL Server para la instancia.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Restablezca el servicio de SQL Server para la instancia.")

<div>


> [!IMPORTANT]  
> Asegúrese de actualizar la configuración del firewall para acomodar el nuevo puerto de SQL Server.



</div>

**Crear y configurar un alias de SQL Server**

1.  Seleccione **Inicio**y elija **Administrador de configuración de SQL Server**, como se muestra en la ilustración siguiente.
    
    ![El icono de SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "El icono de SQL Server Management Studio")

2.  En el panel izquierdo, elija expandir la **instancia de SQL Server**, expanda la configuración de la ** \<versión\> de SQL Native Client**y, a continuación, elija **alias**, como se muestra en la ilustración siguiente.
    
    ![Alias en el administrador de configuración de SQL Server.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Alias en el administrador de configuración de SQL Server.")

3.  Haga clic con el botón secundario en **alias**y seleccione **nuevo alias...**.

4.  Escriba el **nombre del alias**, el **número de Puerto**, el **Protocolo**y el **servidor**, como se muestra en la ilustración siguiente.
    
    ![Crear un nuevo alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Crear un nuevo alias")
    
    <div>
    

    > [!CAUTION]  
    > Asegúrese de escribir el mismo puerto no estándar que usó en el paso anterior, ya que es el puerto en el que se escuchará SQL Server. Si un alias configurado se conecta al FQDN o instancia de SQL Server incorrecto, deshabilite y vuelva a habilitar el protocolo de red asociado. Esto borra la información de conexión almacenada en la memoria caché y permite que el cliente se conecte correctamente.

    
    </div>

**Crear un registro de recursos CNAME de DNS**

1.  Inicie sesión en el equipo que administra DNS.

2.  Seleccione **Inicio**y elija **Administrador del servidor**, como se muestra en la ilustración siguiente.
    
    ![Apertura del administrador del servidor](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Apertura del administrador del servidor")

3.  Seleccione la lista desplegable **herramientas** y, a continuación, seleccione **DNS**, como se muestra en la ilustración siguiente.
    
    ![Abrir DNS desde el administrador del servidor.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Abrir DNS desde el administrador del servidor.")

4.  En el panel izquierdo, expanda el nodo nombre del servidor, expanda el nodo zonas de búsqueda directa y elija el dominio relevante.

5.  Haga clic con el botón secundario en el dominio y seleccione **nuevo alias (CNAME)...**, como se muestra en la ilustración siguiente.
    
    ![Selección de la opción para crear un nuevo alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selección de la opción para crear un nuevo alias CNAME")

6.  Escriba el **nombre del alias** y el **FQDN de SQL Server**, como se muestra en la ilustración siguiente.
    
    ![Rellenar el cuadro de diálogo CNAME de alias nuevo.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Rellenar el cuadro de diálogo CNAME de alias nuevo.")

7.  Elija **Aceptar** para guardar el CNAME y verlo en el administrador de DNS.

</div>

<div>

## <a name="validate-database-connectivity"></a>Validar la conectividad de base de datos

Hay muchas formas diferentes de asegurarse de que funciona. Desea asegurarse de que la base de datos de SQL Server está escuchando en el puerto especificado mediante el alias. Una comprobación rápida se puede completar con los comandos **netstat** y **telnet** .

<div>


> [!NOTE]  
> El cliente Telnet es una característica que se incluye con Windows Server, pero que debe instalarse. Para instalar una característica de Windows Server, abra el administrador del servidor y seleccione Agregar roles y características en el menú administrar.



</div>

**Uso de netstat y Telnet para comprobar la conectividad de la base de datos**

1.  Seleccione **Inicio**y escriba **cmd** para abrir un símbolo del sistema.

2.  Escriba **netstat-a-f**y confirme que SQL Server se está ejecutando con el puerto correcto, tal como se muestra en la ilustración siguiente.
    
    ![Uso de netstat para comprobar el puerto.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Uso de netstat para comprobar el puerto.")

3.  Escriba **Puerto \< \# de nombre\> \<de alias de Telnet** para confirmar la conexión a la instancia de SQL Server. Si la conexión se realiza correctamente, Telnet se conectará y no aparecerá un error. Esto muestra que la instancia de SQL Server está escuchando en el puerto correcto con el alias correcto. Si hay un problema de conexión a la base de datos de SQL Server, Telnet muestra un error que indica que no se puede establecer la conexión. Ahora que ya ha comprobado la conectividad de base de datos en el servidor de bases de datos, puede hacer lo mismo con Lync Server (a través de la red) y asegurarse de que no haya ningún firewall que bloquee el acceso a lo largo del proceso.

</div>

<div>

## <a name="conclusion"></a>Conclusión

Una vez que se haya configurado el alias de SQL Server, puede usarlo para crear una topología de Lync Server 2013 en la herramienta Topology Builder. Para obtener más información acerca de las topologías, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[planeación de la seguridad en Lync Server 2013](lync-server-2013-planning-for-security.md)  
[Definición y configuración de la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md)  
[Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

