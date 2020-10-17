---
title: 'Lync Server 2013: recuperación ante desastres del servidor perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aad1ac0197c4f7755b334624e46f7cec096897f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528827"
---
# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Recuperación ante desastres del servidor perimetral en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-12_

Como con otros roles de servidor, la mejor manera que tiene de proporcionar alta disponibilidad para sus servidores perimetrales es implementar varios servidores perimetrales en grupos de servidores en cada sitio. Si un servidor perimetral deja de funcionar, los demás servidores del grupo de servidores continuarán proporcionando servicios perimetrales.

Para habilitar los procedimientos de recuperación ante desastres, debe tener grupos de servidores perimetrales implementados en sitios independientes. No tiene que emparejar explícitamente grupos de servidores perimetrales como hace con grupos de servidores front-end, pero tener varios grupos de servidores perimetrales ofrece todavía la disponibilidad de continuar si un grupo de servidores perimetrales completo dejar de funcionar. Las secciones siguientes proporcionan detalles sobre la recuperación ante desastres para las distintas funciones de los servidores perimetrales.

<div>

## <a name="remote-access"></a>Acceso remoto

Si tiene varios sitios, cada uno con un grupo de servidores perimetrales, y se produce un error en un grupo de servidores perimetrales completo, los servicios de acceso remoto seguirán funcionando sin necesidad de acciones del administrador. Al crear grupos de servidores perimetrales en sitios diferentes, no se puede usar el mismo FQDN. Cada grupo de servidores perimetrales debe tener FQDN únicos (internos y externos). Los grupos de servidores perimetrales no utilizan reglas de publicación de proxy inverso para comunicarse con los servidores front-end. La conmutación por error automática se produce cuando el cliente vuelve a consultar los registros de servicio DNS de acceso remoto, y los usuarios remotos se enrutan a los servidores perimetrales de otro sitio. El cliente intenta cada FQDN de perímetro externo de acuerdo con la prioridad de los registros DNS SRV.

<div>


> [!NOTE]  
> Para que la conmutación por error funcione sin problemas, asegúrese de que el Firewall permite que los servidores front-end de todos los grupos se comuniquen con todos los servidores perimetrales.



</div>

</div>

<div>

## <a name="federation"></a>Federación

Para las relaciones de Federación con otras organizaciones que ejecutan Lync Server, las solicitudes de Federación de entrada seguirán funcionando siempre que tenga soluciones como GTM de DNS geográfico. Es importante comprender que la conmutación por error de Federación no proporciona conmutación por error con prioridad en los registros SRV. Una solución proporcionada anteriormente puede ayudarle a proporcionar capacidades de recuperación ante desastres para la Federación entrante.

La federación saliente siempre se configura a través de un grupo de servidores perimetrales publicado o un servidor perimetral de la organización. Si este grupo de servidores perimetrales ha quedado inactivo, debe usar el Generador de topologías para cambiar la ruta de federación saliente para que use un grupo de servidores perimetrales que se está ejecutando todavía. Para obtener más información, consulte [conmutación por error del grupo de servidores perimetrales usado para la Federación de Lync Server en Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

</div>

<div>

## <a name="xmpp-federation"></a>Federación XMPP

Para la federación XMPP, se producirá un error tanto en el tráfico entrante como en el saliente si el grupo de servidores perimetrales que está designado como la puerta de enlace de federación XMPP deja de funcionar. Para que la federación XMPP vuelva a funcionar, debe cambiar la federación de XMPP para que use un grupo de servidores perimetrales diferente. Para obtener más información, consulte [conmutación por error del grupo de servidores perimetrales usado para la Federación XMPP en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>Se produce un error en el grupo de servidores perimetrales pero el grupo de servidores front-end todavía se está ejecutando

Si se produce un error en un grupo de servidores perimetrales en un sitio, pero el grupo de servidores front-end de ese sitio todavía se está ejecutando, tendrá que cambiar el grupo de servidores front-end para que use un grupo de servidores perimetrales diferente en un sitio diferente mientras que el primer grupo de servidores perimetrales ha dejado de funcionar. Para obtener más información, consulte [cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end en Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

