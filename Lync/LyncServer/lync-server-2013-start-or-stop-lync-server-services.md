---
title: 'Lync Server 2013: iniciar o detener servicios de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a44e0725aa622b061acc936606bdf2941050952
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a>Iniciar o detener servicios de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Puede usar el panel de control de Lync Server para iniciar o detener todos los servicios de Lync Server 2013 que se ejecutan en un equipo específico o para iniciar o detener un servicio específico.

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>Para iniciar o detener todos los servicios de Lync Server en un equipo

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013. Puede determinar si se le ha asignado el rol de CsServerAdministrator o el rol de RBAC de CsAdministrator ejecutando un comando similar al siguiente:
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.

4.  En la página **Estado** , ordene o busque en la lista según sea necesario para buscar el equipo que ejecuta los servicios que desea iniciar o detener y, a continuación, haga clic en él.

5.  Haga clic en **acción**.

6.  Haga clic en **iniciar todos los servicios** o en **detener todos los servicios**.

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>Para iniciar o detener un servicio específico

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.

4.  En la página **Estado** , ordene o busque en la lista según sea necesario para buscar el equipo que está ejecutando el servicio que desea iniciar o detener y, a continuación, haga clic en él.

5.  Haga clic en **propiedades**.

6.  Ordene la lista de servicios, si es necesario, y haga clic en el servicio que desea iniciar o detener.

7.  Haga clic en **acción**.

8.  Haga clic en **Iniciar servicio** o **Detener servicio**.

9.  Haga clic en **Cerrar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Evitar las sesiones de servicios en Lync Server 2013](lync-server-2013-prevent-sessions-for-services.md)  


[Administración de la topología de Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

