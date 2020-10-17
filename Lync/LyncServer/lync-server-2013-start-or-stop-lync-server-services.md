---
title: 'Lync Server 2013: iniciar o detener los servicios de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ab531875145315b6a505bd0b324e9fdb4d77d5d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532987"
---
# <a name="start-or-stop-lync-server-2013-services"></a>Inicio o detención de los servicios de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Puede usar el panel de control de Lync Server para iniciar o detener todos los servicios de Lync Server 2013 que se ejecutan en un equipo específico o para iniciar o detener un servicio específico.

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>Para iniciar o detener todos los servicios de Lync Server en un equipo:

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013. Puede determinar si se le ha asignado la CsServerAdministrator o el rol RBAC de CsAdministrator ejecutando un comando similar al siguiente:
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Topología** y en **Estado**.

4.  En la página **Estado**, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta los servicios que desea iniciar o detener, y haga clic en él.

5.  Haga clic en **Acción**.

6.  Haga clic en **Iniciar todos los servicios** o **Detener todos los servicios**.

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>Para iniciar o detener un servicio específico:

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Topología** y en **Estado**.

4.  En la página **Estado**, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta el servicio que desea iniciar o detener, y haga clic en él.

5.  Haga clic en **Propiedades**.

6.  Ordene la lista de servicios si es necesario y haga clic en el servicio que desea iniciar o detener.

7.  Haga clic en **Acción**.

8.  Haga clic en **Iniciar servicio** o **Detener servicio**.

9.  Haga clic en **Cerrar**.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Impedir sesiones para servicios en Lync Server 2013](lync-server-2013-prevent-sessions-for-services.md)  


[Administración de la topología de Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

