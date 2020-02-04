---
title: 'Lync Server 2013: restauración de un servidor de servicios de fondo de la edición Enterprise'
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
ms.openlocfilehash: 2bd57054505b3200f63bed8a60c47b400f7e7642
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>Restauración de un servidor de servicios de fondo de la edición empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-18_

Use el procedimiento que se describe en este tema en los dos siguientes casos:

  - Se producen errores en las bases de datos principal y reflejada de un servidor de servicios de fondo con duplicación de Enterprise Edition.

  - Se produce un error en el servidor de servicios de fondo de la edición empresarial que no está reflejado.

Si tiene un back-end de la edición empresarial reflejada y solo se produce un error en el reflejo o la base de datos principal, consulte [restaurar un servidor de back-end de empresa duplicada en Lync server 2013-principal](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) para restaurar la base de datos principal, y [restaurar un servidor back-end empresarial reflejado en Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) para restaurar el reflejo.

Si se produce un error en el almacén de administración central, vea [restaurar el servidor que hospeda el almacén de administración central en Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si se produce un error en un servidor miembro de Enterprise Edition que no es el servidor back-end, consulte [restaurar un servidor miembro de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

<div>


> [!TIP]  
> Le recomendamos que tome una copia de la imagen del sistema antes de comenzar la restauración. Puede usar esta imagen como punto de reversión, en caso de que algo falle durante la restauración. Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>Para restaurar un servidor de servicios de fondo de la edición Enterprise

1.  Empiece con un servidor limpio o nuevo que tenga el mismo nombre de dominio completo (FQDN) que el equipo que ha fallado, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.
    
    <div>
    

    > [!NOTE]  
    > Siga los procedimientos de implementación de servidores de su organización para realizar este paso.

    
    </div>

2.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el servidor que va a restaurar.

3.  Instale SQL Server 2012 o SQL Server 2008 R2, manteniendo los mismos nombres de instancia que antes del error.
    
    <div>
    

    > [!NOTE]  
    > Dependiendo de su implementación, el servidor back-end puede incluir varias bases de datos colocadas o independientes. Siga el mismo procedimiento para instalar SQL Server que usó originalmente para implementar el servidor, incluidos los permisos y los inicios de sesión de SQL Server.

    
    </div>

4.  Después de instalar SQL Server, realice lo siguiente:
    
    1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.
    
    2.  Haga clic en **Descargar topología de la implementación existente**y, a continuación, haga clic en **Aceptar**.
    
    3.  Seleccione la topología y, a continuación, haga clic en **Guardar**. Haga clic en **sí** para confirmar la selección.
    
    4.  Haga clic con el botón derecho en el nodo de **2013 de Lync Server** y, después, haga clic en **publicar topología**.
    
    5.  Siga los instrucciones para **publicar el Asistente de topología** . En la página **crear bases de datos** , seleccione las bases de datos que desea volver a crear.
        
        <div>
        

        > [!NOTE]  
        > Solo se muestran las bases de datos independientes en la página <STRONG>crear bases de datos</STRONG> .

        
        </div>
    
    6.  Si está restaurando un back-end que fue reflejado, continúe siguiendo con el resto del asistente hasta que aparezca el mensaje **crear base de datos de reflejo** . Seleccione la base de datos que desea instalar y complete el proceso.
    
    7.  Siga el resto del asistente y, a continuación, haga clic en **Finalizar**.
    
    <div>
    

    > [!TIP]  
    > En lugar de ejecutar el generador de topología, puede usar el cmdlet <STRONG>install-CsDatabase</STRONG> para crear cada base de datos y el cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar el reflejo. Para obtener más información, consulte la documentación del shell de administración de Lync Server.

    
    </div>

5.  Restaure los datos de usuario al realizar lo siguiente:
    
    1.  Copie ExportedUserData. zip desde $Backup\\ a un directorio local.
    
    2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.
    
    3.  Antes de restaurar los datos de usuario, debe detener los servicios de Lync. Para ello, escriba:
        
            Stop-CsWindowsService
    
    4.  Para restaurar los datos de usuario, en la línea de comandos, escriba:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Por ejemplo:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  Reinicie los servicios de Lync escribiendo:
        
            Start-CsWindowsService

6.  Si ha implementado el grupo de respuesta en este grupo, restaure los datos de configuración del grupo de respuesta. Para obtener más información, consulte [restauración de la configuración de grupo de respuesta en Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

7.  Si está restaurando un servidor back-end que incluye archivar o supervisar bases de datos, restaure los datos de archivado o supervisión mediante una herramienta de SQL Server, como SQL Server Management Studio. Para obtener más información, vea [restaurar o archivar datos en Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

