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
ms.openlocfilehash: 976f486d096f7be59e2eef74eab7b03d6cc4bab0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>Restaurar el servidor que hospeda el almacén de administración central en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Una implementación de Lync Server tiene un único almacén de administración central, una copia de la cual se replica en cada servidor que ejecuta un rol de servidor de Lync Server. En este tema se describe cómo restaurar un servidor de back-end o un servidor Standard Edition que hospeda el almacén de administración central.

Para encontrar el grupo en el que se encuentra el servidor de administración central, abra el generador de topologías, haga clic en **Lync Server**y mire en el panel derecho, en **servidor de administración central**.

Si el servidor back-end que hospeda el almacén de administración central está en una configuración duplicada y la base de datos reflejada sigue funcionando, le recomendamos que haga una copia de seguridad de este reflejo en funcionamiento y, a continuación, realice una restauración completa tanto en la base de datos principal como en la base de datos reflejada con esta copia de seguridad siguiendo el procedimiento de restauración que se muestra a continuación. Esto es necesario porque la restauración de back-end requiere modificar y publicar la topología, lo cual puede hacerse solo si la base de datos principal que hospeda CMS está operativa. Además, tenga en cuenta que las funciones de base de datos principales y reflejadas no se pueden intercambiar si la topología no se puede publicar.

<div>


> [!NOTE]  
> Si se produjo un error en un servidor de back-end o un servidor Standard Edition que no aloja el almacén de administración central, consulte <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">restaurar un servidor de servicios de fondo de la edición empresarial en Lync server 2013</A> o <A href="lync-server-2013-restoring-a-standard-edition-server.md">restaurar un servidor Standard Edition en Lync Server 2013</A>. Si un servidor back-end que hospeda el almacén de administración central está en una configuración reflejada y solo se produjo un error en el reflejo, consulte <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">restaurar un servidor de back-end de empresa duplicada en Lync Server 2013-Mirror</A>. Si se produce un error en cualquier otro servidor, vea <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">restaurar un servidor miembro de Enterprise Edition en Lync server 2013</A>.



</div>

<div>


> [!TIP]  
> Le recomendamos que tome una copia de la imagen del sistema antes de comenzar la restauración. Puede usar esta imagen como punto de reversión, en caso de que algo falle durante la restauración. Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>Para restaurar el almacén de administración central

1.  Empiece con un servidor limpio o nuevo que tenga el mismo nombre de dominio completo (FQDN) que el equipo que ha fallado, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.
    
    <div>
    

    > [!NOTE]  
    > Siga los procedimientos de implementación de servidores de su organización para realizar este paso.

    
    </div>

2.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins y del grupo de administradores locales, inicie sesión en el servidor que va a restaurar.

3.  Si está restaurando un servidor Standard Edition, restaure el almacén de archivos copiando el almacén de archivos adecuado de $Backup a la ubicación del almacén de archivos en el servidor y, a continuación, comparta la carpeta.
    
    <div>
    

    > [!IMPORTANT]  
    > La ruta de acceso y el nombre de archivo del almacén de archivos restaurado deben ser exactamente iguales a los de la copia de seguridad del almacén de archivos para que los componentes que los usan puedan acceder a ellos.

    
    </div>

4.  Siga uno de estos pasos:
    
      - Si va a instalar un servidor Standard Edition, vaya a la carpeta o los elementos multimedia de instalación de Lync Server y, a continuación, inicie el \\asistente\\para\\la implementación de Lync Server, que se encuentra en Setup AMD64 Setup. exe. En el Asistente para la implementación, haga clic en **preparar el primer servidor Standard Edition** y siga el Asistente para instalar el almacén de administración central.
    
      - Si va a instalar un servidor de servicios de fondo para empresas, instale SQL Server 2012 o SQL Server 2008 R2, de modo que los nombres de instancia se mantengan igual que antes del error.
        
        <div>
        

        > [!NOTE]  
        > Según el servidor que esté restaurando y en la implementación, el servidor puede incluir varias bases de datos colocadas o independientes. Siga el mismo procedimiento para instalar SQL Server que usó originalmente para implementar el servidor, incluidos los permisos y los inicios de sesión de SQL Server.

        
        </div>

5.  Desde un servidor front-end, inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

6.  Vuelva a crear el almacén de administración central. En la línea de comandos, escriba lo siguiente:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Por ejemplo:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  Establezca el punto de control de los servicios de dominio de Active Directory para el almacén de administración central. En la línea de comandos, escriba lo siguiente:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Por ejemplo:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > Si pierde el punto de conexión, puede volver a ejecutar este cmdlet.

    
    </div>

8.  Importar los datos de la tienda de administración central desde $Backup. En la línea de comandos, escriba lo siguiente:
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    Por ejemplo:
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  Habilitar los cambios que acaba de hacer. En la línea de comandos, escriba:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Después de habilitar la topología, puede encontrar el documento de topología en la base de datos.

    
    </div>

10. Si está restaurando un servidor de servicios de fondo Enterprise Edition que también ha hospedado el CMS, o si necesita volver a crear un reflejo del CMS, siga este paso. En caso contrario, vaya al paso 11.
    
    Instale las bases de datos independientes de la siguiente manera:
    
    1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.
    
    2.  Haga clic en **Descargar topología de la implementación existente**y, a continuación, haga clic en **Aceptar**.
    
    3.  Seleccione la topología y, a continuación, haga clic en **Guardar**. Haga clic en **sí** para confirmar la selección.
    
    4.  Haga clic con el botón derecho en el nodo de **2013 de Lync Server** y, después, haga clic en **instalar base de datos**.
    
    5.  Siga el Asistente para la **instalación de bases de datos** . Si está restaurando una base de datos que no es el almacén de administración central en este servidor, en la página **crear bases** de datos, seleccione las bases de datos que desea volver a crear.
        
        <div>
        

        > [!NOTE]  
        > Solo se muestran las bases de datos independientes en la página <STRONG>crear bases de datos</STRONG> . Las bases de datos colocadas se crean al ejecutar el Asistente para la implementación de Lync Server.

        
        </div>
    
    6.  Si está restaurando un servidor de servicios de fondo reflejado, siga con el resto del asistente hasta que llegue a la pregunta de crear una base de datos de reflejo. Seleccione la base de datos que desea instalar y complete el proceso.
    
    7.  Siga el resto del asistente y, a continuación, haga clic en **Finalizar**.
    
    <div>
    

    > [!TIP]  
    > En lugar de ejecutar el generador de topología, puede usar el cmdlet <STRONG>install-CsDatabase</STRONG> para crear cada base de datos y el cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar el reflejo. Para obtener más información, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-CsDatabase</A> y <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-CsMirrorDatabase</A>.

    
    </div>

11. Si está restaurando un servidor Standard Edition, vaya a la carpeta o los elementos multimedia de instalación de Lync Server e inicie el Asistente para la implementación \\de\\Lync\\Server que se encuentra en Setup AMD64 Setup. exe. Use el Asistente para la implementación de Lync Server para hacer lo siguiente:
    
    1.  Ejecute el **paso 1: instalar el almacén de configuración local** para instalar los archivos de configuración local.
    
    2.  Ejecute el **paso 2: configurar o quitar los componentes de Lync Server** para instalar los roles de servidor de Lync Server.
    
    3.  Ejecute el **paso 3: solicitar, instalar o asignar certificados** para asignar los certificados.
    
    4.  Ejecute el **paso 4: iniciar servicios** para iniciar servicios en el servidor.
    
    Para obtener más información sobre cómo ejecutar el Asistente para la implementación, consulte la documentación de implementación del rol de servidor que va a restaurar.

12. Restaure los datos de usuario al realizar lo siguiente:
    
    1.  Copie ExportedUserData. zip desde $Backup\\ a un directorio local.
    
    2.  Antes de restaurar los datos de usuario, debe detener los servicios de Lync. Para ello, escriba:
        
            Stop-CsWindowsService
    
    3.  Para restaurar los datos de usuario, en la línea de comandos, escriba:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Por ejemplo:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Reinicie los servicios de Lync escribiendo:
        
            Start-CsWindowsService

13. Restaure los datos de información de ubicación en el almacén de administración central. En la línea de comandos, escriba lo siguiente:
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    Por ejemplo:
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. Si ha implementado el grupo de respuesta en este grupo o servidor Standard Edition, restaure los datos de configuración del grupo de respuesta. Para obtener más información, consulte [restauración de la configuración de grupo de respuesta en Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

15. Si está restaurando un servidor back-end que incluye bases de datos de archivado o supervisión, restaure los datos de archivado o supervisión mediante una herramienta de administración de SQL Server, como SQL Server Management Studio. Para obtener más información, vea [restaurar o archivar datos en Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

