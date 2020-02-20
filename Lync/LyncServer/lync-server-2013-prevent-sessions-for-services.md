---
title: 'Lync Server 2013: impedir sesiones para servicios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b2328e7651c7841cd200bb8e3b78448dfc75e98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services-in-lync-server-2013"></a>Impedir sesiones para servicios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Puede usar el panel de control de Lync Server para evitar nuevas sesiones para todos los servicios de Lync Server 2013 que se ejecutan en un equipo específico o para impedir que se realicen nuevas sesiones para un servicio de Lync Server 2013 específico.

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>Para impedir que se creen sesiones nuevas en todos los servicios de Lync Server en un equipo

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Topología** y después en **Estado**.

4.  En la página **Estado **, clasifique o busque en la lista, según sea necesario, para localizar el equipo que está ejecutando los servicios para los que desea impedir que se creen sesiones nuevas y, a continuación, haga clic en él.

5.  Haga clic en **Acción**.

6.  Haga clic en **Evitar sesiones nuevas en todos los servicios **.

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>Para impedir que se creen sesiones nuevas para un servicio específico

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Topología** y en **Estado**.

4.  En la página **Estado**, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta el servicio que desea iniciar o detener, y haga clic en él.

5.  Haga clic en **Propiedades **.

6.  Clasifique la lista de servicios, si fuera necesario y, a continuación, haga clic en el servicio para el que desea impedir que se creen sesiones nuevas.

7.  Haga clic en **Acción **.

8.  Haga clic en **Evitar sesiones nuevas en el servicio **.

9.  Haga clic en **Cerrar **.

</div>

<div>

## <a name="see-also"></a>Vea también


[Administración de la topología de Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

