---
title: Restauración de un servidor back-end de Enterprise Edition duplicado-Mirror
description: 'Restaurar un servidor back-end de Enterprise Edition reflejado: Mirror.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 011c0aaa10ffed6fef7d579dbc16993fd3341070
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543806"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Restauración de un servidor back-end de Enterprise Edition reflejado en Lync Server 2013-Mirror

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-19_

Si tiene un servidor back-end Enterprise Edition en una configuración reflejada y solo se produce un error en el reflejo, siga los procedimientos descritos en esta sección. Si se produce un error en la base de datos principal y en el reflejo, consulte [restaurar un servidor back-end de Enterprise Edition en Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Si solo se produce un error en el primario, consulte [restaurar un servidor back-end de Enterprise Edition en Lync Server 2013-Primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). Si se produce un error en la base de datos que hospeda el almacén de administración central, vea [restaurar el servidor que hospeda el almacén de administración central en Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si se produce un error en un servidor miembro de Enterprise Edition que no es el servidor back-end, vea [restaurar un servidor miembro de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Le recomendamos que tome una copia de imagen del sistema antes de comenzar la restauración. Puede usar esta imagen como un punto de reversión, en caso de que algo salga mal durante la restauración. Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>Para restaurar una base de datos reflejada del servidor back-end Enterprise Edition

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Desinstalación de la creación de reflejo. En primer lugar, escriba el siguiente cmdlet:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Por ejemplo:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Haga esto para todos los tipos de bases de datos en este servidor.

4.  Cree un servidor nuevo o limpio que tenga el mismo nombre de dominio completo (FQDN) (DB1.contoso.com) que el equipo en el que se produjo el error, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados. Este servidor funcionará como el nuevo reflejo.

5.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el nuevo servidor.

6.  Instale SQL Server 2012 o SQL Server 2008 R2, manteniendo los nombres de instancia iguales que antes del error.

7.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.

8.  Use el generador de topologías para instalar la base de datos reflejada. Realice lo siguiente:
    
      - Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.
    
      - Haga clic con el botón secundario en el nodo Lync Server 2013, haga clic en **topología**y, a continuación, haga clic en **instalar base de datos**.
    
      - Siga el Asistente para **instalar base de datos** . En la página **crear bases de datos** , seleccione las bases de datos que desea volver a crear.
    
      - Siga el asistente hasta que aparezca un mensaje de **creación de base de datos reflejada** . Seleccione la base de datos que desea instalar y complete este proceso.
        
        <div>
        

        > [!TIP]
        > En lugar de ejecutar el generador de topologías, puede usar el cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar la creación de reflejos. Para obtener más información, vea la documentación referente a Lync Server Management Shell.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

