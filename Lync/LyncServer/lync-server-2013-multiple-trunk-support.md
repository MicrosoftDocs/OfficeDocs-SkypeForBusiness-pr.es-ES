---
title: 'Lync Server 2013: compatibilidad con varios tronco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2581ee5f67c6af1c5afd0622f7893ccc2486b51d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507047"
---
# <a name="multiple-trunk-support-in-lync-server-2013"></a>Compatibilidad con varios tronco en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

La funcionalidad de Lync Server 2013 admite varias asociaciones entre puertas de enlace y servidores de mediación. Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red telefónica conmutada (RTC), un controlador de borde de sesión (SBC) o un IP-PBX. Use el generador de topologías para asociar puertas de enlace con servidores de mediación (es decir, troncos).

  - Para asignar o quitar un tronco en Lync Server 2013, primero debe definir un tronco en el generador de topologías. Un tronco se compone de la siguiente Asociación: nombre de dominio completo (FQDN) del servidor de mediación, el puerto de escucha del servidor de mediación, el FQDN de la puerta de enlace y el puerto de escucha de la puerta de enlace.

  - Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación. Esto proporciona resistencia adicional a la infraestructura de Enterprise Voice, lo que es especialmente útil en escenarios de interoperabilidad de central de conmutación (PBX).

Cuando se define un tronco, debe estar asociado con una ruta. Para asociar un tronco a una ruta, defina un nombre sencillo para el tronco en el generador de topologías. Este nombre sencillo se usa como nombre del tronco en el panel de control de Lync Server, donde los troncos pueden asociarse con rutas. El nombre de tronco simple se usa como nombre de puerta de enlace desde el shell de administración de Lync Server.

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

El administrador debe seleccionar un tronco predeterminado asociado a un servidor de mediación. En el generador de topologías, haga clic con el botón secundario en el servidor de mediación asociado y, a continuación, haga clic en **propiedades**. Especifique la puerta de enlace predeterminada para el servidor de mediación.

En el siguiente diagrama se ilustran los distintos troncos definidos para cada servidor de mediación y puerta de enlace.

**Enrutamiento de troncos M-N**

![Varias asignaciones de tronco.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Varias asignaciones de tronco.")

</div>

<span> </span>

</div>

</div>

</div>

