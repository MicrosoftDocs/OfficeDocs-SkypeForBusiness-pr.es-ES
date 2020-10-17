---
title: 'Restauración de un servidor back-end de Enterprise Edition reflejado: principal'
description: 'Restaurar un servidor back-end de Enterprise Edition reflejado: principal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f186bc304dccc363e5a7e0bf89a2276043e361e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542416"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>Restauración de un servidor back-end de Enterprise Edition reflejado en Lync Server 2013-Primary

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-17_

Si tiene un servidor back-end Enterprise Edition en una configuración reflejada y solo se produce un error en la base de datos principal, siga los procedimientos de esta sección. Si se produce un error en la base de datos principal y en el reflejo, consulte [restaurar un servidor back-end de Enterprise Edition en Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Si solo se produce un error en el reflejo, consulte [restaurar un servidor back-end de Enterprise Edition en Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md). Si se produce un error en la base de datos que hospeda el almacén de administración central, vea [restaurar el servidor que hospeda el almacén de administración central en Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si se produce un error en un servidor miembro de Enterprise Edition que no es el servidor back-end, vea [restaurar un servidor miembro de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Le recomendamos que tome una copia de imagen del sistema antes de comenzar la restauración. Puede usar esta imagen como un punto de reversión, en caso de que algo salga mal durante la restauración. Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.

En este tema, la base de datos principal de ejemplo tendrá un nombre de dominio completo (FQDN) de BE1.contoso.com y la base de datos reflejada tendrá un FQDN de BE2.contoso.com.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>Para restaurar una base de datos principal del servidor back-end de Enterprise Edition

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Obligar a todas las bases de datos configuradas a conmutar por error al reflejo. Para cada uno de los tipos de bases de datos que ha configurado en este servidor, escriba el siguiente cmdlet:
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    Por ejemplo:
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > Si ha configurado su base de datos back-end para que use la creación de reflejos sincronizados con un testigo, la conmutación por error es automática.

    
    </div>

4.  Después de completar la conmutación por error, haga lo siguiente:
    
      - Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.
    
      - Deshabilite la creación de reflejos en el servidor back-end: haga clic con el botón secundario en el grupo de **servidores front-end Enterprise Edition** y seleccione **Editar propiedades**. En la pestaña **General** , en **asociaciones**, desactive la casilla **Habilitar la creación de reflejo del almacén de SQL Server** . Haga esto para el archivado y la supervisión según sea necesario. Después, haga clic en **Aceptar**.
    
      - Haga clic con el botón secundario en el nodo Lync Server 2013, haga clic en **topología**y, a continuación, haga clic en **publicar**.
    
      - Seleccione el back-end que sigue funcionando (BE2.contoso.com) para que sea el nuevo almacén de SQL. Para ello, haga clic con el botón secundario en el grupo de **servidores front-end Enterprise Edition** y seleccione **Editar propiedades**. En la pestaña **General** , en **asociaciones**, escriba el FQDN del back-end que funciona en el campo **almacén de SQL Server** (en nuestro ejemplo, BE2.contoso.com).
    
      - Haga clic con el botón secundario en el nodo Lync Server 2013, haga clic en **topología**y, a continuación, haga clic en **publicar**.
    
      - Reinicie los servicios para que cada servidor pueda leer la nueva topología. Desde un shell de administración de Lync Server, ejecute los cmdlets siguientes en cada servidor front-end que pertenezca a este grupo:
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  Desinstalación de la creación de reflejo. Desde un shell de administración de Lync Server, ejecute el siguiente cmdlet:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Por ejemplo:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    Haga esto para todos los tipos de bases de datos en este servidor.

6.  Cree un servidor nuevo o limpio que tenga el mismo FQDN (en este ejemplo, DB1.contoso.com) que el equipo con errores, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados. Este servidor funcionará como el nuevo reflejo.

7.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el nuevo servidor.

8.  Instale SQL Server 2012 o SQL Server 2008 R2, manteniendo los nombres de instancia iguales que antes del error.

9.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.

10. Use el generador de topologías para instalar la BD de reflejo. Realice los siguientes pasos:
    
      - Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.
    
      - Habilite la creación de reflejos en el servidor back-end. Para ello, haga clic con el botón secundario en el grupo de **servidores front-end Enterprise Edition** y seleccione **Editar propiedades**. En la pestaña **General** , en **asociaciones**, active la casilla **Habilitar la creación de reflejo del almacén de SQL Server** . También puede hacerlo para archivado y supervisión, si es necesario.
        
        A continuación, en el campo **reflejo del almacén de SQL Server** , escriba el FQDN del nuevo servidor (n este ejemplo, BE1.contoso.com). Después, haga clic en **Aceptar**.
    
      - Haga clic con el botón secundario en el nodo Lync Server 2013, haga clic en **topología**y, a continuación, haga clic en **instalar base de datos**.
    
      - Siga el Asistente para **instalar base de datos** . En la página **crear bases de datos** , seleccione las bases de datos que desea volver a crear.
    
      - Siga el asistente hasta que llegue al mensaje, **cree una base de datos reflejada**. Seleccione la base de datos que desea instalar y complete este proceso.

</div>

</div>

<span> </span>

</div>

</div>

</div>

