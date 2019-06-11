---
title: 'Restaurar un servidor de servicios de fondo de la edición empresarial duplicada: reflejo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 113d69d7aa39673686ff870c36a64bd1a8fe90f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Restaurar un servidor de servicios de fondo de la edición empresarial duplicada en Lync Server 2013-Mirror

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-19_

Si tiene un servidor de servicios de fondo Enterprise Edition en una configuración reflejada y solo se produce un error en el reflejo, siga los procedimientos descritos en esta sección. Si la base de datos principal y el reflejo fallan, consulte [restaurar un servidor de servicios de fondo de la edición empresarial en Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Si solo se produce un error en el principal, vea [restaurar un servidor back-end de empresa duplicada en Lync server 2013-Primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). Si se produce un error en la base de datos que hospeda el almacén de administración central, consulte [restaurar el servidor que hospeda el almacén de administración central en Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si se produce un error en un servidor miembro de Enterprise Edition que no es el servidor back-end, consulte [restaurar un servidor miembro de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Le recomendamos que tome una copia de la imagen del sistema antes de comenzar la restauración. Puede usar esta imagen como punto de reversión, en caso de que algo falle durante la restauración. Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>Para restaurar una base de datos reflejada del servidor de servicios de fondo de la edición Enterprise

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Desinstalar reflejo. En primer lugar, escriba el siguiente cmdlet:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Por ejemplo:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Haga esto para todos los tipos de base de datos en este servidor.

4.  Cree un servidor limpio o nuevo que tenga el mismo nombre de dominio completo (FQDN) (DB1.contoso.com) que el equipo que ha fallado, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados. Este servidor funcionará como el nuevo reflejo.

5.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el nuevo servidor.

6.  Instale SQL Server 2012 o SQL Server 2008 R2, manteniendo los mismos nombres de instancia que antes del error.

7.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.

8.  Use el generador de topología para instalar la base de datos de reflejo. Realice lo siguiente:
    
      - Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.
    
      - Haga clic con el botón secundario en el nodo de Lync Server 2013, haga clic en **topología**y, a continuación, en **instalar base de datos**.
    
      - Siga el Asistente para la **instalación de bases de datos** . En la página **crear bases de datos** , seleccione las bases de datos que desea volver a crear.
    
      - Siga el asistente hasta que aparezca un mensaje de creación de una **base de datos de reflejo** . Seleccione la base de datos que desea instalar y complete este proceso.
        
        <div>
        

        > [!TIP]
        > En lugar de ejecutar el generador de topologías, puede usar el cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar el reflejo. Para obtener más información, consulte la documentación del shell de administración de Lync Server.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

