---
title: Impedir sesiones para servicios
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19f3ed7c788db120782966541bfea9813328d90c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a>Impedir sesiones para servicios

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Puede usar el panel de control de Microsoft Lync Server 2010 para evitar nuevas sesiones para todos los servicios de Lync Server 2010 que se ejecutan en un equipo específico o para evitar nuevas sesiones para un servicio específico de Lync Server 2010.

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>Para evitar nuevas sesiones para todos los servicios de Lync Server en un equipo

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.

2.  Abra el Panel de control de Lync Server.

3.  En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.

4.  En la página **Estado** , ordene o busque en la lista según sea necesario para buscar el equipo que ejecuta los servicios para los que desea evitar nuevas sesiones y, a continuación, haga clic en ella.

5.  Haga clic en **acción**.

6.  Haga clic en **evitar nuevas sesiones para todos los servicios**.

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>Para evitar nuevas sesiones para un servicio específico

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.

2.  Abra el Panel de control de Lync Server.

3.  En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.

4.  En la página **Estado** , ordene o busque en la lista según sea necesario para buscar el equipo que está ejecutando el servicio que desea iniciar o detener y, a continuación, haga clic en él.

5.  Haga clic en **propiedades**.

6.  Si es necesario, ordene la lista de servicios y haga clic en el servicio para el que desea evitar nuevas sesiones.

7.  Haga clic en **acción**.

8.  Haga clic en **evitar nuevas sesiones para el servicio**.

9.  Haga clic en **Cerrar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

