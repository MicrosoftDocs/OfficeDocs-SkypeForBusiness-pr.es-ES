---
title: 'Lync Server 2013: restauración de un servidor back-end de Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1da289a6c0cf73e1466acdf28a74b1fbce76251a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>Restauración de un servidor back-end de Enterprise Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-18_

Use el procedimiento descrito en este tema en los dos casos siguientes:

  - Se produce un error en las bases de datos principal y reflejada de un servidor back-end de Enterprise Edition reflejado.

  - Se produce un error en un servidor back-end de Enterprise Edition que no es reflejado.

Si tiene un back-end de Enterprise Edition reflejado y solo se produce un error en el reflejo o la base de datos principal, consulte [restaurar un servidor back-end de Enterprise Edition en Lync server 2013-Primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) para restaurar la base de datos principal y [restaurar un servidor back-end de Enterprise Edition en Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) para restaurar el reflejo.

Si se produce un error en el almacén de administración central, consulte [restaurar el servidor que hospeda el almacén de administración central en Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si se produce un error en un servidor miembro de Enterprise Edition que no es el servidor back-end, vea [restaurar un servidor miembro de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

<div>


> [!TIP]  
> Le recomendamos que tome una copia de imagen del sistema antes de comenzar la restauración. Puede usar esta imagen como un punto de reversión, en caso de que algo salga mal durante la restauración. Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>Para restaurar un servidor back-end Enterprise Edition

1.  Empiece con un servidor nuevo o limpio que tenga el mismo nombre de dominio completo (FQDN) que el equipo con error, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.
    
    <div>
    

    > [!NOTE]  
    > Siga los procedimientos de implementación de servidores de la organización para realizar este paso.

    
    </div>

2.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el servidor que va a restaurar.

3.  Instale SQL Server 2012 o SQL Server 2008 R2, manteniendo los nombres de instancia iguales que antes del error.
    
    <div>
    

    > [!NOTE]  
    > Según la implementación, el servidor back-end puede incluir varias bases de datos combinadas o independientes. Para instalar el servidor SQL Server, siga el mismo procedimiento que usó originalmente para implementar el servidor, incluidos los permisos e inicios de sesión de SQL Server.

    
    </div>

4.  Tras instalar SQL Server, haga lo siguiente:
    
    1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.
    
    2.  Haga clic en **Descargar topología de la implementación existente** y haga clic en **Aceptar**.
    
    3.  Seleccione la topología y, a continuación, haga clic en **Guardar**. Haga clic en **Sí** para confirmar la selección.
    
    4.  Haga clic con el botón secundario en el nodo **Lync Server 2013** y, a continuación, haga clic en **publicar topología**.
    
    5.  Siga el asistente **Publicar la topología**. En la página **crear bases de datos** , seleccione las bases de datos que desea volver a crear.
        
        <div>
        

        > [!NOTE]  
        > En la página <STRONG>Crear bases de datos</STRONG> solo se muestran bases de datos independientes.

        
        </div>
    
    6.  Si está restaurando un back-end que fue reflejado, continúe para seguir el resto del asistente hasta que aparezca la **base de datos de creación de reflejos** del mensaje. Seleccione la base de datos que desea instalar y complete el proceso.
    
    7.  Siga los pasos restantes del asistente y, a continuación, haga clic en **Finalizar**.
    
    <div>
    

    > [!TIP]  
    > En lugar de ejecutar el generador de topologías, puede usar el cmdlet <STRONG>install-CsDatabase</STRONG> para crear cada base de datos y el cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar la creación de reflejos. Para obtener más información, vea la documentación referente a Lync Server Management Shell.

    
    </div>

5.  Para restaurar los datos del usuario, lleve a cabo el siguiente procedimiento:
    
    1.  Copie ExportedUserData. zip de $Backup\\ a un directorio local.
    
    2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.
    
    3.  Antes de restaurar los datos de usuario, debe detener los servicios de Lync. Para ello, escriba:
        
            Stop-CsWindowsService
    
    4.  Para restaurar los datos del usuario, en la línea de comandos, escriba:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Por ejemplo:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  Reinicie Lync Services escribiendo lo siguiente:
        
            Start-CsWindowsService

6.  Si implementó el grupo de respuesta en este grupo, restaure los datos de configuración del grupo de respuesta. Para obtener más información, consulte [restore Response Group Settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

7.  Si desea restaurar un servidor back-end que incluye bases de datos de archivado o supervisión, restaure los datos de archivado o supervisión con una herramienta de SQL Server, como SQL Server Management Studio. Para obtener más información, consulte [restauración de la supervisión o archivado de datos en Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

