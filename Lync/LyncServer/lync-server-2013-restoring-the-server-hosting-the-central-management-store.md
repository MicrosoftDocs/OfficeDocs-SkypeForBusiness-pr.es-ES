---
title: 'Lync Server 2013: restaurar el servidor que hospeda el almacén de administración central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01d3912402b48ce8aede4a53efea208c96bff825
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511397"
---
# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>Restauración del servidor que hospeda el almacén de administración central en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Una implementación de Lync Server tiene un solo almacén de administración central, una copia de la cual se replica en cada servidor que ejecuta un rol de servidor de Lync Server. En este tema se describe cómo restaurar un servidor back-end o un servidor Standard Edition que hospede el almacén de administración central.

Para encontrar el grupo de servidores en el que se encuentra el servidor de administración central, abra el generador de topologías, haga clic en **Lync Server**y mire en el panel derecho del **servidor de administración central**.

Si el servidor back-end que hospeda el almacén de administración central está en una instalación reflejada y la base de datos reflejada sigue funcionando, le recomendamos que realice una copia de seguridad de este reflejo que sigue funcionando y, a continuación, realice una restauración completa en la base de datos principal y en la base de datos reflejada, mediante el siguiente procedimiento de restauración. Esto es necesario porque la restauración de back-end requiere modificar y publicar la topología, y esto solo puede realizarse si el CMS de hospedaje de la base de datos principal está operativo. Además, tenga en cuenta que las funciones de base de datos principal y reflejada no se pueden intercambiar si no se puede publicar la topología.

<div>


> [!NOTE]  
> Si se produce un error en un servidor back-end o un servidor Standard Edition que no hospeda el almacén de administración central, consulte <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">restaurar un servidor back-end de Enterprise Edition en Lync server 2013</A> o <A href="lync-server-2013-restoring-a-standard-edition-server.md">restaurar un servidor Standard Edition en Lync Server 2013</A>. Si un servidor back-end que hospeda el almacén de administración central está en una configuración reflejada y solo se produjo un error en el reflejo, consulte <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">restaurar un servidor back-end de Enterprise Edition en Lync Server 2013-Mirror</A>. Si se produce un error en cualquier otro servidor, vea <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">restaurar un servidor miembro de Enterprise Edition en Lync server 2013</A>.



</div>

<div>


> [!TIP]  
> Le recomendamos que tome una copia de imagen del sistema antes de comenzar la restauración. Puede usar esta imagen como un punto de reversión, en caso de que algo salga mal durante la restauración. Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>Para restaurar el almacén de administración central

1.  Empiece con un servidor nuevo o limpio que tenga el mismo nombre de dominio completo (FQDN) que el equipo con error, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.
    
    <div>
    

    > [!NOTE]  
    > Siga los procedimientos de implementación de servidores de la organización para realizar este paso.

    
    </div>

2.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins y del grupo local Administradores, inicie sesión en el servidor que va a restaurar.

3.  Si va a restaurar un servidor Standard Edition, restaure el almacén de archivos copiando el almacén de archivos adecuado de $Backup a la ubicación del almacén de archivos en el servidor y, a continuación, compartiendo la carpeta.
    
    <div>
    

    > [!IMPORTANT]  
    > La ruta de acceso y el nombre de archivo del almacén de archivos restaurados deben ser exactamente los mismos que los del almacén de archivos de copia de seguridad para que los componentes que usan los archivos puedan acceder a ellos.

    
    </div>

4.  Realice una de las siguientes acciones:
    
      - Si va a instalar un servidor Standard Edition, vaya a la carpeta o los medios de instalación de Lync Server y, a continuación, inicie el Asistente para la implementación de Lync Server que se encuentra en la \\ instalación de \\ AMD64 \\Setup.exe. En el Asistente para la implementación, haga clic en **preparar el primer servidor Standard Edition** y siga el Asistente para instalar el almacén de administración central.
    
      - Si va a instalar un servidor back-end empresarial, instale SQL Server 2012 o SQL Server 2008 R2, manteniendo los nombres de instancia iguales que antes del error.
        
        <div>
        

        > [!NOTE]  
        > Según el servidor que vaya a restaurar y en la implementación, el servidor puede incluir varias bases de datos colocadas o independientes. Para instalar SQL Server siga el mismo procedimiento que usó originalmente para implementar el servidor, incluyendo los inicios de sesión y los permisos de SQL Server.

        
        </div>

5.  En un servidor front-end, inicie el shell de administración de Lync Server: haga clic en **Inicio**, **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

6.  Vuelva a crear el almacén de administración central. En la línea de comandos, escriba lo siguiente:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Por ejemplo:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  Establezca el punto de control de servicios de dominio de Active Directory para el almacén de administración central. En la línea de comandos, escriba lo siguiente:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Por ejemplo:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > Si pierde el punto de conexión, puede volver a ejecutar este cmdlet.

    
    </div>

8.  Importe los datos del almacén de administración central desde $Backup. En la línea de comandos, escriba lo siguiente:
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    Por ejemplo:
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  Habilite los cambios que acaba de realizar. En la línea de comandos, escriba:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Una vez habilitada la topología, podrá encontrar el documento de topología en la base de datos.

    
    </div>

10. Si va a restaurar un servidor back-end Enterprise Edition que también hospeda el CMS, o si necesita volver a crear un reflejo del CMS, siga este paso. De lo contrario, vaya al paso 11.
    
    Para instalar las bases de datos independientes, haga lo siguiente:
    
    1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.
    
    2.  Haga clic en **Descargar topología de la implementación existente** y haga clic en **Aceptar**.
    
    3.  Seleccione la topología y, a continuación, haga clic en **Guardar**. Haga clic en **Sí** para confirmar la selección.
    
    4.  Haga clic con el botón secundario en el nodo **Lync Server 2013** y, a continuación, haga clic en **instalar base de datos**.
    
    5.  Siga el Asistente para **instalar base de datos** . Si va a restaurar una base de datos que no sea el almacén de administración central en este servidor, en la página **crear bases** de datos, seleccione las bases de datos que desea volver a crear.
        
        <div>
        

        > [!NOTE]  
        > En la página <STRONG>Crear bases de datos</STRONG> solo se muestran bases de datos independientes. Las bases de datos colocadas se crean al ejecutar el Asistente para la implementación de Lync Server.

        
        </div>
    
    6.  Si va a restaurar un servidor back-end reflejado, siga con el resto del asistente hasta que llegue a un mensaje de creación de una base de datos reflejada. Seleccione la base de datos que desea instalar y complete el proceso.
    
    7.  Siga los pasos restantes del asistente y, a continuación, haga clic en **Finalizar**.
    
    <div>
    

    > [!TIP]  
    > En lugar de ejecutar el generador de topologías, puede usar el cmdlet <STRONG>install-CsDatabase</STRONG> para crear cada base de datos y el cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar la creación de reflejos. Para obtener más información, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-CsDatabase</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-CsMirrorDatabase</A>.

    
    </div>

11. Si va a restaurar un servidor Standard Edition, vaya a la carpeta o los medios de instalación de Lync Server e inicie el Asistente para la implementación de Lync Server que se encuentra en la \\ instalación de \\ AMD64 \\Setup.exe. Use el Asistente para la implementación de Lync Server para hacer lo siguiente:
    
    1.  Ejecute el **Paso 1: Instalar el almacén de configuración local** para instalar los archivos de configuración local.
    
    2.  Ejecute el **paso 2: configurar o quitar los componentes de Lync Server** para instalar los roles de servidor de Lync Server.
    
    3.  Ejecute el **Paso 3: Solicitar, instalar o asignar certificados** para asignar los certificados.
    
    4.  Ejecute el **Paso 4: Iniciar servicios** para iniciar los servicios en el servidor.
    
    Para obtener más información sobre cómo ejecutar el Asistente para la implementación, consulte la documentación de implementación del rol de servidor que va a restaurar.

12. Para restaurar los datos del usuario, siga el siguiente procedimiento:
    
    1.  Copie ExportedUserData.zip de $Backup \\ a un directorio local.
    
    2.  Antes de restaurar los datos de usuario, debe detener los servicios de Lync. Para ello, escriba:
        
            Stop-CsWindowsService
    
    3.  Para restaurar los datos del usuario, en la línea de comandos, escriba:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Por ejemplo:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Reinicie Lync Services escribiendo lo siguiente:
        
            Start-CsWindowsService

13. Restaurar datos de información de ubicación en el almacén de administración central. En la línea de comandos, escriba lo siguiente:
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    Por ejemplo:
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. Si implementó el grupo de respuesta en este grupo de servidores o servidor Standard Edition, restaure los datos de configuración del grupo de respuesta. Para obtener más información, consulte [restore Response Group Settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

15. Si va a restaurar un servidor back-end que incluye bases de datos de archivado o supervisión, restaure los datos de archivado o supervisión con una herramienta de administración de SQL Server, como SQL Server Management Studio. Para obtener más información, consulte [restauración de la supervisión o archivado de datos en Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

